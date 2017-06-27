# /usr/bin/ethereum_genoil
## Installation of cpp-ethereum (Genoil) on Ubuntu 16.04
Make sure universe is enable in /etc/apt/sources.list

```
apt-get install -y wget vim

wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb

add-apt-repository -y ppa:ethereum/ethereum

apt-get update

apt-get install -y git cmake libcryptopp-dev libleveldb-dev libboost-all-dev \
  libgmp-dev libreadline-dev libcurl4-gnutls-dev ocl-icd-libopencl1 opencl-headers mesa-common-dev \
  build-essential libjsoncpp-dev libjsonrpccpp-dev libmicrohttpd-dev cuda

cd
git clone https://github.com/Genoil/cpp-ethereum.git
cd cpp-ethereum/
mkdir build
cd build
cmake -DBUNDLE=cudaminer ..
make -j$(nproc)
```
