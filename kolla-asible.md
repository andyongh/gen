
# ALL in One Openstack for Development

### Kolla Asible for Openstack on CentOS 7.0 VM

## install Guide
https://docs.openstack.org/kolla-ansible/latest/user/quickstart.html

## Don't use virtual ENV of Python

## using --ignore-installed to skip package install error

pip install -r kolla/requirements.txt
pip install -r kolla-ansible/requirements.txt

## precheck error:
TypeError: load_config() got an unexpected keyword argument 'config_dict'
 -- Downgrading to docker==2.7.0 using pip install "docker<3" solves the issue
 
 
 ## prechecks error on ip
 
 modify /etc/kolla/globals.yml
 enable_haproxy = no
 network_interface = eth0
 
his should be a VIP, an unused IP on your network that will float between
 the hosts running keepalived for high-availability. If you want to run an
 All-In-One without haproxy and keepalived, you can set enable_haproxy to no
 in "OpenStack options" section, and set this value to the IP of your
 'network_interface' as set in the Networking section below.

