Vagrant.configure("2") do |config|
  config.vm.box = "dummy"

  config.vm.provider :aws do |aws, override|
    aws.access_key_id = ENV['AWS_ACCESS_KEY_ID']
    aws.secret_access_key = ENV['AWS_SECRET_ACCESS_KEY']
    aws.keypair_name = ENV['AWS_SSH_KEY_ID']
    aws.session_token = ENV['AWS_SESSION_TOKEN']

    aws.ami = "ami-6678ee5c" #AMI for EBS Backed ParaVirtual ubuntu-precise-12.04-amd64-server-20130204 instance ap-southeast-2
    aws.region = "ap-southeast-2"
    aws.instance_type = "m1.small" #Smallest size for ParaVirtual instance
    aws.subnet_id = "subnet-f9b76a9c" #VPC Subnet

    #Tags
    aws.tags = {
      'Name' => 'vagrant-webdev'
    }

    override.ssh.username = "ubuntu"
    override.ssh.private_key_path = ENV['AWS_SSH_KEY_PATH']
  end

  #There is minimal support for synced folders
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: ".git/"

  #Bootstrap webserver
  config.vm.provision :shell, path: "bootstrap.sh"
end