# swift

[![Build Status](https://travis-ci.com/huan/swift.svg?branch=master)](https://travis-ci.com/huan/swift)
[![Docker Pulls](https://img.shields.io/docker/pulls/zixia/swift.svg?maxAge=2592000)](https://hub.docker.com/r/zixia/swift/)

Tensorflow Swift Docker Image

## Docker

```sh
docker run -ti --rm \
  --privileged \
  --userns=host \
  \
  -v "$(pwd)":/notebooks \
  --entrypoint /bin/bash \
  zixia/swift
```

See: <https://github.com/hashicorp/nomad/issues/1904#issuecomment-523295864>

## AUTHOR

[@huan](https://github.com/huan) [Huan LI](https://linkedin.com/in/zixia) \<zixia@zixia.net\>

<a href="http://stackoverflow.com/users/1123955/zixia">
  <img src="http://stackoverflow.com/users/flair/1123955.png" width="208" height="58" alt="profile for zixia at Stack Overflow, Q&amp;A for professional and enthusiast programmers" title="profile for zixia at Stack Overflow, Q&amp;A for professional and enthusiast programmers">
</a>

## COPYRIGHT & LICENSE

- Code & Docs © 2018 - now Huan LI \<zixia@zixia.net\>
- Code released under the Apache-2.0 License
- Docs released under Creative Commons
