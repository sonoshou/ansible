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

### vagrant用の実行

```
$ cd ~/ansible
# ansible-playbook vagrant.xml --check # dry-run
# ansible-playbook vagrant.xml
```
