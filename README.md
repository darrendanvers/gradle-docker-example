# A Docker Multi-Stage Build using Gradle

This is a demonstration of using Gradle in a Docker multi-stage build. The application itself is trivial. It exists
just to show setting up a Docker container to run a Gradle build.

### Running the Multi-Stage Build

On a command line, type in `docker build -t gradle-docker-example:v1 .`.

Type in `docker system prune` to remove the intermediate containers.

### Running the Built Image

On the command line, type in `docker run --rm gradle-docker-example:v1`.

### Naming and Tagging the Build Container

The container that did the actual build will be unnamed. If you want to give it a name and tag, 
type in `docker build -t gradle-docker-build:v1 --target build-image .`.

### Important Files

The [Dockerfile](Dockerfile) contains all the valuable code in this example.

### Helpful Links

I extracted this example from a larger project I was working on. Below are some documents I was referring
to while doing that work.

[Docker's build documentation](https://docs.docker.com/engine/reference/commandline/build/).

[Docker's multi-stage build documentation](https://docs.docker.com/develop/develop-images/multistage-build/).

[The Gradle image documentation on Dockerhub](https://hub.docker.com/_/gradle).

I was able to build a lot of this example based on [Paul Bakker's example](http://paulbakker.io/java/docker-gradle-multistage/).

[This thread](https://github.com/moby/moby/issues/34151) has a good discussion about why the intermediate images are saved
but are not named.
