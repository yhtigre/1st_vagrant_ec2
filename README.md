# 1st_vagrant_ec2

## 概要
【基本】VagrantでEC2をプロビジョニングする。

## 事前準備
事前にVagrantの導入、AWSのアカウント登録等が必要。

### Vagrantに関する事
1. Vagrantを導入する

```Bash
$ sudo yum install vagrant
```

2. Vagrantプラグインを導入する

```Bash
$ vagrant plugin install vagrant-aws
$ vagrant plugin install dotenv
```

### AWSに関する事
1. AWSアカウントの新規作成
2. AWSアクセスキーの作成


