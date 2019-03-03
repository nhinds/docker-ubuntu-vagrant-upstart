# nhinds/ubuntu-vagrant-upstart

Ubuntu docker image running upstart/ssh for use with vagrant.

[Docker Hub](https://hub.docker.com/r/nhinds/ubuntu-vagrant-upstart)

## Tags

* `14.04` - Ubuntu trusty

## Usage

### From vagrant

```
  config.vm.provider :docker do |docker|
    docker.image = 'nhinds/ubuntu-vagrant-upstart:14.04'

    docker.has_ssh = true
  end
```

### Manual

Run in the background:

    docker run --rm -d nhinds/ubuntu-vagrant-upstart:14.04

Then use `docker exec` to run `bash` or other commands within the container

    docker exec -it <container name> bash

It is not recommended to use this image for non-Vagrant purposes, since it sets up the `vagrant` user with Vagrant's insecure SSH key by default.
