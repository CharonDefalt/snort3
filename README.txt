#ubuntu-20.04.6-live-server-amd64 NEED THIS

apt update

apt install build-essential libpcap-dev libpcre3-dev libnet1-dev zlib1g-dev luajit hwloc libdnet-dev libdumbnet-dev bison flex liblzma-dev openssl libssl-dev pkg-config libhwloc-dev cmake cpputest libsqlite3-dev uuid-dev libcmocka-dev libnetfilter-queue-dev libmnl-dev autotools-dev libluajit-5.1-dev libunwind-dev

mkdir snort-source-files

cd snort-source-files

tar xvzf libdaq-3.0.13.tar.gz

cd libdaq

./bootstrap
./configure
make
make install

cd ..

tar xzf gperftools-2.9.1.tar.gz

cd gperftools-2.8/
./configure
make
make install

cd ..

tar xzf 3.1.28.0.tar.gz

cd snort3-3.1.28.0

./configure_cmake.sh --prefix=/usr/local --enable-tcmalloc

cd build
make
make install

ldconfig

snort -V
