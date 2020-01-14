# network-studies

### commands and brief summary:
- printf (~$ man printf) -> can format strings
- netcat (~$ man nc) ->  can be used to talk with servers on tcp protocol (transport layer).

##### netcat listen and call
`listen: ~$ nc -l 2345`\
`connecting: ~$ nc localhost 2345`\
`(both host and client can communicate anything text on tcp)`

##### netcat listen e redirect to google.com when connect via webbrowser
`~$ printf 'HTTP/1.1 302 Moved\r\nLocation: http://www.google.com' | nc -l 2345`
