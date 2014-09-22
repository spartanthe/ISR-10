ISR-10
======

##ISR-10 INTERCAL Servlet 1.0
(First draft)

###What is a INTERCAL Servlet?
INTERCAL program supporting communication with hosting environment via stdin and stdout using communication protocol.
Note that it's common practice to use INTERCAL Servlet-s written in not such powerful languages for rapid prototyping and then rewrite servlets in pure INTERCAL before release.
However leaving such non-pure INTERCAL Servlet-s in production or distributing them to customer is considered a bad practice.

What is a INTERCAL Servlet Container?
The servlet container is a part of a Web server or application server that processes requests to .i files, compiles them and in these rare cases when succeeds compiling loads the program establishes stdin-stdout communication with her in a way described below and reads out whatever that program has to say.
Because INTERCAL is designed to be with safety in mind it's very likely that servlet container is written not in INTERCAL language.

###Handling HTTP Requests

URL patterns (request path):
```
	.../program.i
	.../program.i/1
	.../program.i?x=1&x=2
	.../program.i/multiply?x=1&y=2
```

###Communication between INTERCAL Servlet and INTERCAL Container

```
(All below is optional and is up to a programmer who writes servlet)
DO WRITE IN VERB (todo: quite a lame name for GET,POST,PUT,DELETE...)
  << GET
DO WRITE IN RESOURCE
  << multiply
DO WRITE IN HTTP VERSION IF YOU THINK I CARE
  << HTTP/1.1
DO WRITE IN ARGUMENT
  << x=1
DO WRITE IN ARGUMENT
  << y=2
DO WRITE IN ARGUMENT
  <<
DO WRITE IN HEADER IF YOU THINK I CARE
(same story)
PLEASE NOTE THAT I START PROCESSING THE REQUEST
PLEASE NOTE THAT I START READING OUT
LET RESPONSE BE HTTP/I.I CC OK
LET OUTPUT BE IN PLAIN TEXT
PLEASE CALCULATE CONTENT LENGTH FOR ME
PLEASE NOTE THAT I START READING OUT BODY
(body follows...)
ANOTHER JOB WELL DONE, DON'T FORGET TO CHECK CONTENT LENGTH
```

###Etiquette for communication between servlet and container

(Usage of PLEASE)
