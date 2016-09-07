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
|Gitlab and Mattermost Server|OS|CentOS6.8||
||Code managemnt tool|GitlabCE ver.8.11.2||
||Chat tool|Mattermost ver.3.30|on GitlabCE|
|Jenkins2 Server|OS|CentOS6.8||
||CI Tool|Jenkins ver.2.19||

## Usage
If you use Vagrant with Virtualbox and Ansible(ver.2.1 highre),
you just run following commands.

```
git clone 
cd 
vagrant up
```
