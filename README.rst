==============================
Parallel Text Processing Tools
==============================

A collection of small, efficient tools for parallel processing of text 
files at the Unix command line.

pcat
----

	$ pcat file1 file2... fileN

pcat (parallel cat) reads files in parallel and writes whole, intact 
lines to standard out. This is most useful if those files are actually 
pipes from other processes: pcat will start reading them all 
simultaneously, without blocking, and make sure they don't clobber each 
other's output.  If you've ever tried to combine the output from 
multiple processes and just got mashed gobbledygook, you'll appreciate 
pcat. Every line it outputs is an entire line from exactly one input.  
The order of the output is arbitrary, except that lines from the same 
source retain their order.


Building
========

The tools are written in ISO C99 and can be built with the included 
Makefile.  Functional tests can be run with ``make test``; the tools 
have only been tested on Linux and feedback on other platforms is 
welcome.