# optimisation

This mini project will see us look into how we can begin to optimise our Dockerfile's, as well as
take a closer look at how the layering functionality works and how we can leverage this layering
functionality to provide more concise Dockerfile's which can be built into the requisite images
faster, easier and provide better legibility so for future people it's easier to refactor.

1) Build the provided Dockerfile
2) Observe the error

```bash
$ docker build -t optimisation ./
```

Why is this erroring? How would we know this by looking at the code. How can we prevent this?

After we can spot the easy mistake, we then need to think about how to make this easier. By referring
to our previous bash knowledge, how can we refactor this `Dockerfile` with a simple update to no
longer error?

Make the required fix, and then re-build and run the container

```bash
$ docker build -t optimisation ./
$ docker run optimisation
```

This Dockerfile is reasonably simple, however we are still not doing an awful lot. So let's make our
project a little more complex

1) Create a simple shell file, that will output a simple echo message
2) Leave your Dockerfile AS IS, but add an ignore file so all document files don't get copied
into the container
3) Tell your Dockerfile by default to execute the shell file on demand when running your container
4) Re-build your docker image
5) Re-run your container and observe it all works

Once this all runs and does what you expect lets now start analysing our docker images and finding
out more information about them.

To start with run the following commands. Observing the output at each stage and discussing what
each item means

```bash
$ docker images
$ docker ps
$ docker system df
$ docker help
# This next command will require input from the user after submission
$ docker system prune
```

After we have ran these commands and discussed. We can then discuss how to optimise our build.

To begin with we have little to no additional items installed onto our docker image, so lets begin
by adding a few more things

1) Add `curl`, `gcc` and `build-essential` as packages to your docker build
2) Install bundler as a gem (Provide a specific version)
3) Check your new image size (It should be bigger)

Now we have began to start experimenting with adding things, it makes sense to also start looking
into removing things (i.e. making things more optimal, hence the mini-project name).

To begin with reduce down the fat ruby 2.7 build to an alpine build, by adding `-alpine` at the end
of the `FROM` reference

Try to re-build the image. You'll notice some things will start going wrong. Again discuss what the
problem/s might be, and how you could fix them?

To finish on, attempt to fix the existing Dockerfile by creating an alpine version of the same
Dockerfile, give it a different name (i.e. `Dockerfile-alpine`), and then try to build this version
of the container.

Once you have done this, compare the size of the two different containers (Fat vs Thin), and then
realise when Devops asks you to use alpine containers how much space you could save.
