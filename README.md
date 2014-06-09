tftsrv
======

Tiny File Transmit SeRVice/SeRVer (fake httpd).

tftsrv and tftsrv2 behave like httpd, but always respond same data.

* tftsrv : one shot (respond data, and then exit).
* tftsrv2 : not one shot (to stop, use Ctrl-c or kill(1)).

License
-------

zlib License.

Set up
------

1. Install nc(1) (netcat). tftsrv and tftsrv2 need nc(1).
2. Put tftsrv/tftsrv2 to a directory registered in PATH.
2. Modify tftsrv/tftsrv2 to configure some variables.

| name     | synopsis                                  | description                     |
|:---------|:------------------------------------------|:--------------------------------|
| nccmd    | nccmd &ltlisten-port&gt                   | nc(1) in listen mode.           |
| httpecho | httpecho &ltstring-with-c-style-escape&gt | echo command for HTTP response. |


Usage
-----

Please check help message `tftsrv -h` and `tftsrv2 -h`

Example
-------

```sh
# Listen in port 5432, and respond somefile.
tftsrv -f somefile

# Listen in port 8086, and respond stdin data.
some-command | tftsrv2 -p 8086
```
