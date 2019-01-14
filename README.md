# MacOSX10.11.sdk.tar.gz
MacOSX10.11.sdk.tar.gz for Bitcoin

# qtumx 0.16
1. git clone --recursive https://github.com/qtumproject/qtum-enterprise.git qtum
2. cp qtum/contrib/gitian-build.py .
3. ./gitian-build.py --setup -c zsrem qtumx_beta_0.16.0
4. ./bin/make-base-vm --suite trusty --arch amd64 --lxc
5. wget https://github.com/zsrem/MacOSX10.11.sdk.tar.gz/raw/master/MacOSX10.11.sdk.tar.gz -P gitian-builder/inputs/
6. ./gitian-build.py --detach-sign --no-commit -b -c -o lwm -j 8 -m 8000 -u "/home/ubuntu/Build/qtum" zsrem qtumx_beta_0.16.0 
