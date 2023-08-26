# What

Alma/Rocky/RHEL 8 and 9 do not have ndisc6 published to any official repos.  No one seems to own the packaging of ndisc6 for these platforms these days.  This should fill the gap.A

## Building

For Alma/Rocky/RHEL glibc-static is in the Power Tools repo and that may need to be enabled with `dnf config-manager --set-enabled powertools`

```
dnf -q -y install rpmdevtools git glibc-static
dnf -q -y groupinstall "Development Tools"
git clone https://github.com/mtimm/ndisc6-rpm ndisc6-rpm
cd ./ndisc6-rpm
./build.sh
```

## Installing on the build machine

```
sudo rpm -i ~/rpmbuild/RPMS/*/*.rpm
```