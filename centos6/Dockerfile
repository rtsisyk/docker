FROM centos:6
MAINTAINER Roman Tsisyk <roman@tarantool.org>

# http://people.centos.org/tru/devtools-1.1/readme
RUN curl http://people.centos.org/tru/devtools-1.1/devtools-1.1.repo -o /etc/yum.repos.d/devtools-1.1.repo
RUN yum -y install devtoolset-1.1
RUN yum -y install yum-utils rpm-build rpmdevtools
RUN yum -y install sudo vim wget mc git
RUN sed -i.bak -n -e '/^Defaults.*requiretty/ { s/^/# /;};/^%wheel.*ALL$/ { s/^/# / ;} ;/^#.*wheel.*NOPASSWD/ { s/^#[ ]*//;};p' /etc/sudoers

RUN echo "source /opt/centos/devtoolset-1.1/enable" > /etc/profile.d/devtoolset-1.1.sh
# Needed for rpmbuild
ENV CC=/opt/centos/devtoolset-1.1/root/usr/bin/gcc
ENV CXX=/opt/centos/devtoolset-1.1/root/usr/bin/g++

ENV LC_ALL="en_US.UTF-8" LANG="en_US.UTF-8"

# Deps for tarantool
RUN yum -y install cmake readline-devel binutils-devel libyaml-devel
# Deps for lua modules
RUN yum -y install lua lua-devel
