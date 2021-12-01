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
