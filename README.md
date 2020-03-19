# Modbus debugging utility - runs on UNIX, Linux or Windows command line

A command line utility to connect to a Modbus TCP server, issue
function codes and receive the response.

Written in Python 3.

Runs on UNIX, Linux and Windows.

## Demo video

A video showing the Modbus TCP debug utility in action:

[Modbus TCP debug utility](https://youtu.be/qAe64vMbH-w)

It is approximately three and a half minutes long.

## Running

On UNIX and Linux make sure the `mbdebug.py` file is executable:

```
chmod a+x mbdebug.py
```

and then run as follows:

```
./mbdebug.py
```

On Windows run as follows:

```
python mbdebug.py
```

When the following prompt appears:

```
MB>
```

the program is ready for use.

## Connecting to a Modbus TCP server

At the `MB>` prompt type:

```
host <hostname>
connect
```

where `<hostname>` is the host name or IP address of the Modbus TCP server
you want to connect to.

## Sending a request

Type a sequence of commands similar to:

```
fc 3
addr 256
data 8
show
send
```

The `fc 3` specifies function code 3 (read hold holding registers).
The `addr 256` specifies a register address of 256.  The `data 8`
instructs the server to return the 8 word values held at register
addresses 256 to 263 inclusive.  The `show` displays the packet
bytes about to be sent and a human readable break down of the bytes.
Finally the `send` sends the packets and waits for a response.

## Quitting the program

Type `q` or `quit` at the `MB>` prompt.  If there is an active connection it
will be closed before the program exists.

## Notes

This tool is for debugging a Modbus TCP server and NOT to be used
in a production environment for critical monitoring or (shudder) device
control.  You have been warned!

-------------------------------------------------------------

End of README.md
