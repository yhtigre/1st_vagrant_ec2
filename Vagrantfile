# -*- mode: ruby -*-
# vi: set ft=ruby :

require "dotenv"
Dotenv.load

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "dummy"
  config.vm.box_url = "https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box"
  config.vm.synced_folder "./samples", "/vagrant", type: "rsync", disabled: false

  config.vm.provider :aws do |aws, override|
    aws.access_key_id = ENV["AWS_ACCESS_KEY_ID"]
    aws.secret_access_key = ENV["AWS_SECRET_ACCESS_KEY"]
    aws.keypair_name = ENV["AWS_KEYPAIR_NAME"]
    aws.security_groups = ENV["AWS_SECURITY_GROUP"]

    aws.instance_type = "t2.micro"
    aws.region = "ap-northeast-1"
    aws.ami = "ami-4af5022c"
    aws.tags = {
      'Name' => 'ec2-vagrant-test'
    }

    override.ssh.username = "ec2-user"
    override.ssh.private_key_path = ENV["AWS_SSH_PRIVATE_KEY_PATH"]
  end
end
