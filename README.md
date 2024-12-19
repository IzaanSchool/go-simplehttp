## Simple HTTP server written in golang
Simple webserver in golang, to demonstrate basic functionalities like e.g. sending back some request header info, the local IP address of the container and how to include the usage of environment variables.

### what does it do?

This container starts a webserver on port 8000 and returns back 
- some header information
- the local ip address of the container
- the message provided by environment variable called _message_  

to start _simplehttp_ web server , map local port 8000 into container and provide the env variable **message**:  
```bash
docker build -t simplegoapp .
docker run -p 8000:8000 simplegoapp
```  

output from above call (your IP address will vary):  
```bash
GET / HTTP/1.1
Header["User-Agent"] = ["curl/7.58.0"]
Header["Accept"] = ["*/*"]
Host = "localhost:8000"
RemoteAddr = "172.17.0.1:36540"

===> local IP: "172.17.0.2"

Env message = Hello

``` 