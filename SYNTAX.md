# Dockerfile syntax

Each line in a Dockerfile is prefixed with a command keyword and then has a method signature

Below is a **non-exhaustive** list of the command keywords and what they do. For a full list
consult the official docker docs site

`FROM` - Use this command followed by a link to the reference base image you wish to use

`MAINTAINER` - Use this command to specify some metadata about who has maintained the docker image
(This isn't really that useful in most situations) 

`COPY` - Use this command to run the equivalent of a `cp` command in bash. However this copies a file
from the host system into the docker system. Often people will copy more than just one file.

`ADD` - This is similar / functionally equivalent to copy, but also will untar an archive, as well
as perform basic HTTP get requests if you pass in a source directory that is a url

`RUN` - Run an arbitrary command. Often used to set up a specific state in your image so that when
you spin up a container instance, certain state/s are guaranteed

`USER` - Sets the default username / usergroup. Often used to ensure access state in specific
situations so you know that when you are running a program you will generate files with the correct
access privileges

`WORKDIR` - Sets the default Working directory. NB: This is not the same as `$PWD` and as such this
often is set to be a different arbitrary value so that when you enter the container you will know
what directory you will be in.

`CMD` - Sets the default command that will be executed once the image has **finished** booting up
and the container is running

`ENV` - Sets a single environment variable (Often you will want to set many of these). These can
also be passed in at run-time, more often than not a combination of the two is used.
