# 概要

自分用のサーバのansible管理。

## 主な管理対象

### common

- システムアカウントの追加
- 基本ソフトウェアをyumでインストール

### webserver

- nginxのインストール
- システムアカウントにrbenvをインストール

## ansibleの実行

### 前提

- CentOS 7.0系

### ansibleのインストール

```
# yum install epel-release
# yum install ansible
```

Amazon Linuxの場合

```
# amazon-linux-extras install epel
# yum --enablerepo=epel install ansible
```

### git clone

```
$ cd ~
$ git clone https://github.com/sonoshou/ansible.git
```

### ansibleの実行

```
$ cd ~/ansible
# ansible-playbook site.xml --check # dry-run
# ansible-playbook site.xml
```

### サーバ用の実行

- ユーザ名を変更
  - インストール先のユーザ名に変更する

```
$ vim ~/ansible/vars/standard.xml
```

```
$ cd ~/ansible
# ansible-playbook 00_standard.xml --check # dry-run
# ansible-playbook 00_standard.xml
```

### vagrant用の実行

```
$ cd ~/ansible
# ansible-playbook 00_vagrant.xml --check # dry-run
# ansible-playbook 00_vagrant.xml
```

## エラーの対応

### 1. ansibleで使用するpythoの指定 

```
If you require Python 3 support use the `dnf` Ansible module instead.
```

この場合は以下の `vars` を読み込む。

```
vars/ansible-python-path.yml
```
