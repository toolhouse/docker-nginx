# nginx docker images

This is a [Toolhouse][toolhouse] fork of the [official Docker image for nginx][upstream], with changes that make it  more appropriate as a base image. 

The images are kept as close as possible to the official images. See the [official image readme][upstream-readme] for documentation. 

## Differences from the Official Docker Image

- __Only port 80 is exposed.__ The official Docker image exposes port 80 and 443, even though the bundled nginx configuration does not listen on 443. This can cause issues with many tools which setup monitoring and/or health checks based on the ports exposed by Docker. As images cannot un-export ports exposed by a base image this is problematic such cases. See pull request [docker-nginx/130][nginx-pull-request] and issue [docker/3465][docker-issue] for background and discussion on this.

[toolhouse]: http://toolhouse.com
[upstream]: https://registry.hub.docker.com/_/nginx/
[upstream-readme]: https://github.com/docker-library/docs/tree/master/nginx

[nginx-pull-request]: https://github.com/nginxinc/docker-nginx/pull/130
[docker-issue]: https://github.com/docker/docker/issues/3465
