# Gunrock Web Server
This web server is a simple server used in ECS 150 for teaching about multi-threaded programming and operating systems. This version of the server can only handle one client at a time and simply serves static files.

## Quickstart
To compile and run the server, open a terminal and execute the following commands:
```bash
$ git clone https://github.com/kingst/gunrock_web.git
$ cd gunrock_web
$ make
$ ./gunrock_web
```

To test it out, you can either open up a web browser on the same machine and give it this url `http://localhost:8080/hello_world.html` or if you want to use curl on the command line you can test it out like this:
```bash
$ # get a basic HTML file
$ curl http://localhost:8080/hello_world.html
$ # get a basic HTML file with more detailed information
$ curl -v http://localhost:8080/hello_world.hml
$ # test out a file that does not exist (404 status code)
$ curl -v http://localhost:8080/hello_world2.html
$ # test out a POST, which isn't supported currently (405 status code)
$ curl -v -X POST http://localhost:8080/hello_world.html
```

## Command line arguments
Coming soon!

## Key files
To make this server multithreaded, you're going to need to modify the main `gunrock.cpp` file. You'll need to modify this file so that client requests are handled by a pool of threads with some priority logic to handle high priority files first. See the project README for more details.

## Other files