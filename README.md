# 1st_vagrant_ec2

## 概要
VagrantでEC2をプロビジョニングする。

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
3. EC2キーペアの作成(公開鍵)
4. EC2セキュリティグループの作成
5. EC2キーペア(秘密鍵)の設置

## 使い方
1. GitHubリポジトリからローカル環境へクローンする

```Bash
$ git clone https://github.com/yhtigre/1st_vagrant_ec2.git
```

2. .envファイルの環境変数へパラメータを設定する

```Bash
AWS_ACCESS_KEY_ID = ""
AWS_SECRET_ACCESS_KEY = ""
AWS_KEYPAIR_NAME = ""
AWS_SECURITY_GROUP = ""
AWS_SSH_PRIVATE_KEY_PATH = ""
```

3. EC2インスタンスを生成する

```Bash
$ vagrant up --provider=aws
Bringing machine 'default' up with 'aws' provider...
==> default: Warning! The AWS provider doesn't support any of the Vagrant
==> default: high-level network configurations (`config.vm.network`). They
==> default: will be silently ignored.
==> default: Launching an instance with the following settings...
==> default:  -- Type: t2.micro
==> default:  -- AMI: ami-4af5022c
==> default:  -- Region: ap-northeast-1
==> default:  -- Keypair: vagrant
==> default:  -- Security Groups: ["vagrant"]
==> default:  -- Block Device Mapping: []
==> default:  -- Terminate On Shutdown: false
==> default:  -- Monitoring: false
==> default:  -- EBS optimized: false
==> default:  -- Source Destination check: 
==> default:  -- Assigning a public IP address in a VPC: false
==> default:  -- VPC tenancy specification: default
==> default: Waiting for instance to become "ready"...
==> default: Waiting for SSH to become available...
==> default: Machine is booted and ready for use!
==> default: Rsyncing folder: /home/yh/waste/1st_vagrant_ec2/samples/ => /vagrant
$
```

4. EC2インスタンスへSSHログインする

```Bash
$ vagrant ssh

       __|  __|_  )
       _|  (     /   Amazon Linux AMI
      ___|\___|___|

https://aws.amazon.com/amazon-linux-ami/2017.03-release-notes/
11 package(s) needed for security, out of 26 available
Run "sudo yum update" to apply all updates.
Amazon Linux version 2017.09 is available.
[ec2-user@ip-172-31-18-142 ~]$
```

5. EC2インスタンスを破棄する

```Bash
$ vagrant destroy -f
==> default: Terminating the instance...
$
```

