# docker-swift-tensorflow

[![Build Status](https://travis-ci.com/huan/docker-swift.svg?branch=master)](https://travis-ci.com/huan/docker-swift)
[![Docker Pulls](https://img.shields.io/docker/pulls/zixia/swift.svg?maxAge=2592000)](https://hub.docker.com/r/zixia/swift/)
[![Docker Layers](https://images.microbadger.com/badges/image/zixia/swift.svg)](https://microbadger.com/#/images/zixia/swift)

[![dockeri.co](https://dockeri.co/image/zixia/swift)](https://hub.docker.com/r/zixia/swift/)

Tensorflow Swift Docker Image based on [Swift-Jupyter](https://github.com/google/swift-jupyter).

## Usage

### CLI

```sh
nvidia-docker run -ti --rm \
  --privileged \
  --userns=host \
  \
  -v "$(pwd)":/notebooks \
  --entrypoint /bin/bash \
  zixia/swift
```

> `--privileged` and `--userns=host` might be required for some docker deamon configuration. (see [this issue](https://github.com/hashicorp/nomad/issues/1904#issuecomment-523295864))

### Jupyter

```bash
nvidia-docker run -ti --rm \
  -p 8888:8888 \
  --cap-add SYS_PTRACE \
  -v "$(pwd)":/notebooks \
  zixia/swift
```

The functions of these parameters are:

- `-p 8888:8888` exposes the port on which Jupyter is running to the host.
- `--cap-add SYS_PTRACE` adjusts the privileges with which this container is run, which is required for the Swift REPL.
- `-v <host path>:/notebooks` bind mounts a host directory as a volume where notebooks created in the container will be stored.  If this command is omitted, any notebooks created using the container will not be persisted when the container is stopped.

## Develop

### Testing

After building the docker image according to the instructions above,

```sh
docker run --rm \
  --cap-add SYS_PTRACE \
  zixia/swift \
  python3 /swift-jupyter/test/all_test_docker.py
```

## History

### v0.1 (22 Aug 2019)

Init version based on [Swift-Jupyter](https://github.com/google/swift-jupyter), working under Ubuntu 19.04 without any problem.

## Resources

- [Swift-Jupyter](https://github.com/google/swift-jupyter)
- [Dockerized Swift for TensorFlow and advanced usage examples.](https://github.com/zachgrayio/swift-tensorflow)
- [Swift for tensorflow using GPU with nvidia docker](https://forums.fast.ai/t/swift-for-tensorflow-using-gpu-with-nvidia-docker/44730)

## Author

[Huan](https://github.com/huan) [(李卓桓)](https://linkedin.com/in/zixia) \<zixia@zixia.net\>

<a href="http://stackoverflow.com/users/1123955/zixia">
  <img src="http://stackoverflow.com/users/flair/1123955.png" width="208" height="58" alt="profile for zixia at Stack Overflow, Q&amp;A for professional and enthusiast programmers" title="profile for zixia at Stack Overflow, Q&amp;A for professional and enthusiast programmers">
</a>

## Copyright & License

- Code & Docs © 2018 - now Huan LI \<zixia@zixia.net\>
- Code released under the Apache-2.0 License
- Docs released under Creative Commons
