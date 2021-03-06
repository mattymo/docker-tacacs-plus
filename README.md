# TACACS+ Docker Image

This image is a built version of [tac_plus](http://www.pro-bono-publico.de/projects/), a TACACS+ implementation written by Marc Huber.

## Building

Docker engine 17.06+ is required to build this image because it uses a multi-stage build.
To build run: `docker build -t tac_plus .`.

## Using

To run with the default configuration:

```
docker run --name tac_plus -d -p 49:4949 lfkeitel/tacacs_plus:latest
```

The default configuration has a user with the username:password of admin:admin and the enable password is set to enable. Obviously, don't use this configuration in production.

The configuration is located at `/etc/tac_plus/tac_plus.cfg`. If you wish to use a custom configuration, simply overwrite it in a derived image or use a volume mount.

By default logs go to stdout.

Port 49 is exposed as the server port.

## Configuration

Configuration documentation can be found [here](http://www.pro-bono-publico.de/projects/unpacked/doc/tac_plus.pdf).

## License

The LICENSE file in this repository is for the build scripts and built Docker image.

This image includes software developed by Marc Huber (Marc.Huber@web.de).

The tac_plus and supporting software is under a different license which can be found [here](http://www.pro-bono-publico.de/projects/unpacked/LICENSE).