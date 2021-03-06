Cloud-Init
##########

Cloud-Init YAML files for use with Nutanix events, blog articles & posts.

Please feel free to use these for your own environments if you find them useful.

20190513_centos7toolsvm.yaml
............................

Cloud-Init YAML for setting up a very basic CentOS 7 VM.  Intended for use with lab environments.

Repos:

- epel-release for CentOS/RHEL 7

Packages:

- Python 3.6
- Python 3.6 setup tools
- Python **pip**
- stress
- awscli
- s3cmd
- ntp
- ntpdate
- nodejs
- bash-completion
- unzip
- make
- gcc-c++
- jq

Configures:

- User named **nutanix** with password **nutanix/4u**.
- SSH public key for the **nutanix** user.  Note that you will need to populate the ssh-authorized-keys field with YOUR public key.
- NPM packages **express** and **request**.
- Stops and disables **firewalld** (shouldn't don't do this in production).
- Sets **selinux** to **disabled** (shouldn't do this in production, either).
- Upgrades **pip** to latest version.
- Configures **ntp** via **ntpdate** (Cloud-Init **ntp** module is not used here).
- Updates and upgrades all packages
- Sets the VM hostname to **centos7-tools-vm**

Support
-------

These cloud-init YAML files are *unofficial* and are not supported or actively maintained by Nutanix in any way.

In addition, please also be advised that these YAML files may deploy packages or configure options that do not follow best practices.  Please check through each YAML file to ensure the configuration suits your requirements.

**Changes will be required before these YAML files can be used in production environments.**