Make a chroot centos8 stream
===
    dir=/home/z/centos8
    wget http://mirror.centos.org/centos/8-stream/BaseOS/x86_64/os/Packages/centos-stream-release-8.6-1.el8.noarch.rpm

# make yum repo
    rpm --root=$dir --rebuilddb
    rpm --root=$dir --nodeps -i centos-stream-release-8.6-1.el8.noarch.rpm

# signature
    cp -r /etc/pki $dir/etc/pki
# the follow files are missing, I don't know if there is a official way to create that.
    cp -r /etc/yum.repo.d $dir/etc/
    cp -r /etc/dnf/vars/* $dir/etc/dnf/vars/*
# install a minimal base system
    yum --installroot=$dir update
    yum --installroot=$dir install -y yum
