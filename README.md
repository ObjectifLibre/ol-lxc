## lxc-centos: LXC template for CentOS

This template create a CentOS container on Debian/Ubuntu.

It supports CentOS 5 and 6, i386 and x86_64 architectures.

To create a new CentOS 6 container (same arch as the host):

`````
$ sudo lxc-create -n centos1 -t centos
`````

A few options are available:

`````
$ sudo lxc-create -n c1 -t centos -- -h
template-specific help follows: (these options follow '--')
usage:
    /usr/share/lxc/templates/lxc-centos -n|--name=<container_name>
        [-r|--release=<5|6>]
        [-a|--arch=<i386|x86_64>]
        [-p|--path=<path>]
        [-R|--repo=<repository_URL>]
        [-h|--help]
Mandatory args:
  -n,--name         container name, used to as an identifier for that container from now on
Optional args:
  -r,--release      which release to install (5 or 6), defaults to 6
  -a,--arch         architecture of the container (i386 or x86_64), defaults to host architecture
  -p,--path         path to where the container rootfs will be created, defaults to /var/lib/lxc.
  -R,--repo         URL of the repository where rpm packages can be found, defaults to CentOS mirrors
  -h,--help         print this help
`````

To create a CentOS 5 container using a local mirror:
`````
$ sudo lxc-create -n c1 -t centos -- -r 5 -R http://mirrors/centos/6/os/x86_64
`````
