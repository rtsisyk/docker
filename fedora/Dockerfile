FROM fedora:rawhide
MAINTAINER Roman Tsisyk <roman@tarantool.org>

RUN dnf -y group install 'Development Tools'
RUN dnf -y group install 'C Development Tools and Libraries'
RUN dnf -y group install 'RPM Development Tools'
RUN dnf -y install fedora-packager fedora-review
RUN dnf -y install sudo vim wget mc
RUN sed -i.bak -n -e '/^Defaults.*requiretty/ { s/^/# /;};/^%wheel.*ALL$/ { s/^/# / ;} ;/^#.*wheel.*NOPASSWD/ { s/^#[ ]*//;};p' /etc/sudoers

# Deps for tarantool
RUN dnf -y install cmake readline-devel binutils-devel libyaml-devel
# Deps for lua modules
RUN dnf -y install luajit luajit-devel lua lua-devel

ENV LC_ALL="en_US.UTF-8" LANG="en_US.UTF-8"
# Fix paths for mock
ENV PATH /usr/bin:/usr/sbin:/bin:/sbin
