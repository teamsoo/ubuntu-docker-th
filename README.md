# Ubuntu Docker TH
Built on top of [official Ubuntu](https://registry.hub.docker.com/_/ubuntu/) images.

Image specific:
- [openssh-server](https://help.ubuntu.com/community/SSH/OpenSSH/Configuring)

Config:

  - `PermitRootLogin yes`
  - `UsePAM no`
  - exposed port 22
  - default command: `/usr/sbin/sshd -D`
  - root password: `root`
  - change mirror to `th`

## Run example

```bash
$ docker build -t ubuntu_th ./16.04/
$ docker run -d -p 2222:22 -P --name test_th_ubuntu ubuntu_th
$ ssh root@localhost -p 2222
# The password is `teamsoo`
root@test_ubuntu $
```
