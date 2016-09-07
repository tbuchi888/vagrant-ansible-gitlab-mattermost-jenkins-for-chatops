# vagrant-ansible-gitlab-mattermost-jenkins-for-chatops
## Summary
This repository is Ansible-playbook and Vagrantfile to build ChatOps environment of OSS on-Premise.
And this ChatOps uses following OSS on CentOS6.
- Gitlab
- Mattermost
- Jenkins2

Then,
I introduce concrete setting methods after this environmental construction with Japanese technical blog as follows.
http://qiita.com/tbuchi888/items/fa02a10728999520e1a0

## Env.
I validated this repository in the following environment.

|Type|Item|Detial|Note|
|:-:|:-:|:-:|:-:|
|HOST|OS|OSX Yosemite||
||Hypervisor|Virtualbox5.14||
||building tool|Vagrant1.8.5||
|||Ansible 2.1.0 update:2016/04/20|Because I use the yumrepository module, version 2.10 or more of Ansible are necessary.|
|Gitlab and Mattermost Server|OS|CentOS6.8|The Box of Vagrant is [geerlingguy/centos6](https://atlas.hashicorp.com/geerlingguy/boxes/centos6)(*1)|
||Host name|mygitlab|Change your environment(*2)|
||IPaddress|192.168.33.131|Change your environment(*2)|
||Code managemnt tool|GitlabCE ver.8.11.2||
||Chat tool|Mattermost ver.3.30|on GitlabCE|
|Jenkins2 Server|OS|CentOS6.8|The Box of Vagrant is [geerlingguy/centos6](https://atlas.hashicorp.com/geerlingguy/boxes/centos6)(*1)|
||Host name|myjenkins|Change your environment(*2)|
||IPaddress|192.168.33.132|Change your environment(*2)|
||CI Tool|Jenkins ver.2.19||

Note!
- *1: The Box of Vagrant is [geerlingguy/centos6](https://atlas.hashicorp.com/geerlingguy/boxes/centos6) in atlas.hashicorp.com. Change your environment box in `conf-vbox-guestvm.yml` if you want to use your box.
- *2: Change your environment, `conf-vbox-guestvm.yml` and `/etc/hosts`.
And then, if you only use Ansible(without Vagrant)  add `hosts.yml` too.

## Usage
If you use Vagrant with Virtualbox and Ansible(higher ver.2.1 ),
You only type to following in commands.

Add hosts for these servers. 
Example `sudo vi /etc/hosts`

```
192.168.33.131  mygitlab
192.168.33.132  myjenkins
```

And then,

```
git clone https://github.com/tbuchi888/vagrant-ansible-gitlab-mattermost-jenkins-for-chatops.git
cd vagrant-ansible-gitlab-mattermost-jenkins-for-chatops
vagrant up
```
