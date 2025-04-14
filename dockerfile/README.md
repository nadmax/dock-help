# Dockerfile
A Dockerfile is a text document containing all the instructions a user could call on the command line to create a Docker image.  
Instructions are not case-sensitive. However, convention is for them to be uppercase to distinguish them from arguments more easily.

Here's the instructions you can use:
| Instruction   | Description                                               |
|---------------|-----------------------------------------------------------|
| ADD           | Add local or remote files and directories.                |
| ARG           | Use build-time variables.                                 |
| CMD           | Specify default commands.                                 |
| COPY          | Copy files and directories.                               |
| ENTRYPOINT    | Specify default executable.                               |
| ENV           | Set environment variables.                                |
| EXPOSE        | Describe which ports your application is listening on.    |
| FROM          | Create a new build stage from a base image.               |
| HEALTHCHECK   | Check a container's health on startup.                    |
| LABEL         | Add metadata to an image.                                 |
| ONBUILD       | Specify instructions for when the image is used in a build. |
| RUN           | Execute build commands.                                   |
| SHELL         | Set the default shell of an image.                        |
| STOPSIGNAL    | Specify the system call signal for exiting a container.   |
| USER          | Set user and group ID.                                    |
| VOLUME        | Create volume mounts.                                     |
| WORKDIR       | Change working directory.                                 |

[View the Dockerfile example here](https://github.com/nadmax/dock-help/blob/master/dockerfile/Dockerfile.example)