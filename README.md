# Docker Containers

My personal containers used for development.

Usage:

    dockerdo DOCKER_IMAGE_TAG command [args]

Example:

    # Host system
    roman@desktop:$ head -n3 /etc/os-release
    PRETTY_NAME="Debian GNU/Linux stretch/sid"
    NAME="Debian GNU/Linux"
    ID=debian

    # Docker container
    roman@desktop:$ ./dockerdo rtsisyk/env:fedora head -n3 /etc/os-release
    NAME=Fedora
    VERSION="24 (Rawhide)"
    ID=fedora
