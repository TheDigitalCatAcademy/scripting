# Scripting support files

This repository contains files used for the scripting modules of the DevOps course.

## Build the Docker image

Once you have the repository cloned locally move into that directory and run the following commands (remember the `$` is a generic prompt and you should not type it)

```
$ docker build -t devops_ubuntu .
```

Once this command has been terminated successfully the Docker image is ready to be executed.

## Run the Docker image

You can run the Docker image with

```
$ docker run -t -i -v $(pwd):/opt/devops devops_ubuntu /bin/bash
```

This runs an the image that you already built (`devops_ubuntu`) in an interactive mode (`-i -t`), executing the shell `/bin/bash`. The current directory will be accessible under `/opt/devops` (thanks to `-v $(pwd):/opt/devops`).

After you run the command you should see a new, very essential prompt like

```
root@5105b5472e86:/#
```

Please note that the number that follows the `@` sign in the prompt is the ID of the running Docker container, so it will be different for you. This prompt means that you are inside the container and you are successfully running the bash shell. Congratulations!

Move to the directory that contains the example files inside the container

```
root@5105b5472e86:/# cd /opt/devops/
root@5105b5472e86:/opt/devops# ls
Dockerfile  README.md  scripting1
```

As you can see when you run `ls` you get a list of the files contained in the directory `/opt/devops`. Since we shared the directory of the repository with the Docker container, you should see the same file there.

As I mentioned, the number after the symbol `@` will change every time the image is run. In the next lessons I will drop the whole prompt `root@XXXXXXXXXXXX:/#` and use `$` instead.

To exit the Docker image, just type `exit` and hit Enter.
