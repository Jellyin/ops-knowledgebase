## GitLab Runner

GitLab Runner is the open source project that is used to run your jobs and send the results back to GitLab. It is used in conjunction with GitLab CI, the open-source continuous integration service included with GitLab that coordinates the jobs.

## Requirements

GitLab Runner is written in Go and can be run as a single binary, no language specific requirements are needed.

It is designed to run on the GNU/Linux, macOS, and Windows operating systems. Other operating systems will probably work as long as you can compile a Go binary on them.

If you want to use Docker make sure that you have version v1.5.0 at least installed.

 

## Features

####  Allows to run:

- multiple jobs concurrently
- use multiple tokens with multiple server (even per-project)
- limit number of concurrent jobs per-token

#### Jobs can be run:

- locally
- using Docker containers
- using Docker containers and executing job over SSH
- using Docker containers with autoscaling on different clouds and virtualization hypervisors
- connecting to remote SSH server



Is written in Go and distributed as single binary without any other requirements

Supports Bash, Windows Batch and Windows PowerShell

Works on GNU/Linux, OS X and Windows (pretty much anywhere you can run Docker)

Allows to customize the job running environment

Automatic configuration reload without restart

Easy to use setup with support for Docker, Docker-SSH, Parallels or SSH running environments

Enables caching of Docker containers

Easy installation as a service for GNU/Linux, OSX and Windows

Embedded Prometheus metrics HTTP server

 

## Install GitLab Runner

#### Docker install：

	docker run -d --name gitlab-runner --restart always \ -v /srv/gitlab-runner/config:/etc/gitlab-runner \ -v /var/run/docker.sock:/var/run/docker.sock \ gitlab/gitlab-runner:latest



#### Register GitLab Runner

docker exec -i gitlab-runner gitlab-runner register -n -u <gitlab url> -r <gitlab runner token> --name <runner name> --executor docker --docker-image <image> --tag-list docker,aws

#### Advanced Configuration

	https://docs.gitlab.com/runner/configuration/advanced-configuration.html

