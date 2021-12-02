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


## DONE UP TO HERE ## 
Once we have done all of this I want you to optimise the 2nd Dockerfile again

1) Copy all files from our host to the image. Find a way of launching docker so you can "check"
this has been done correctly
2) Copy all files from our host to the image **except** documentation files that end in `.md`.
Again make sure we can check and verify this has been done. (NB: There is a quick way to do this)
3) Run the 2nd Docker container that you made, but run the 1st shell script (`hello.sh`).
Do this **without** editing the 1st `Dockerfile`

Once you have done all this, take a break. This completes the mvp exercise. The next exercise to
look into is optimisation
