# mvp

To start with in this first Mini-Project let us do the following

1) Read the simple Dockerfile
2) Build the Docker Image
3) Run the sample image to spin up a container, observe what is happening

```bash
$ docker build -t mvp ./
$ docker run mvp
```

Once you have gotten the following to run. We will come back and chat about what we have observed.
In particular what looks "wrong".

Now let's take this a step further, creating our own Dockerfile that is slightly more optimal
that will run a different bash script.

1) Create a new Dockerfile similar to the last one, but call it Dockerfile2
2) Create a new shell script. Call it whatever you want, but make sure it outputs something different
3) Build your new improved version of the mvp project
4) Run the sample image to spin up a container, observe what is happening

```bash
$ docker build -f Dockerfile2 -t mvp2 ./
$ docker run mvp2
```

Now we have gotten two different `Dockerfile`'s to work lets work on optimising things and making
things a little bit more dynamic. Through researching lets see how we can do the following

1) Set an environment variable inside the `Dockerfile`
2) Set an environment variable at runtime (Check the docs for the short-hand flag for this)
3) Set an environment variable both inside the `Dockerfile` and at runtime. Which takes precedence?
4) Tell Docker to expect an environment variable, but don't define it. What does it equal?
5) Globally expose an environment variable on your host OS, then Tell Docker to expect an environment
variable, and don't define it. What does it now equal?

Once we have done all of this I want you to optimise the 2nd Dockerfile again

1) Copy all files from our host to the image. Find a way of launching docker so you can "check"
this has been done correctly
2) Copy all files from our host to the image **except** documentation files that end in `.md`.
Again make sure we can check and verify this has been done. (NB: There is a quick way to do this)
3) Run the 2nd Docker container that you made, but run the 1st shell script (`hello.sh`).
Do this **without** editing the 1st `Dockerfile`

Once you have done all this, take a break. This completes the mvp exercise. The next exercise to
look into is optimisation
