# vagrant-webdev-template-aws
Vagrant - Ubuntu 12.04 LTS 64-bit box; Web Server installed, enabled

```bash
git clone https://github.com/lantrix/vagrant-webdev-template-aws.git
cd vagrant-webdev-template-aws
vagrant plugin install vagrant-aws
vagrant box add dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
vagrant up --provider=aws
```
http://{Elastic IP}
