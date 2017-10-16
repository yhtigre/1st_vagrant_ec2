# 1st_vagrant_ec2

## 概要
【基本】VagrantでEC2をプロビジョニングする。

## 事前準備
事前にVagrantの導入、AWSのアカウント登録等が必要。

#### Vagrantに関する事
1. Vagrantを導入する

```Bash
$ sudo yum install vagrant
```

2. Vagrantプラグインを導入する

```Bash
$ vagrant plugin install vagrant-aws
$ vagrant plugin install dotenv
```

#### AWSに関する事
1. AWSアカウントの新規作成
2. AWSアクセスキーの作成
3. EC2キーペアの作成(公開鍵)
4. EC2セキュリティグループの作成
5. EC2キーペア(秘密鍵)の設置

## 使い方
1. GitHubリポジトリからローカル環境へクローンする

```Bash
$ git clone https://github.com/yhtigre/1st_vagrant_ec2.git
```

