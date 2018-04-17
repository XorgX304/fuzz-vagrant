Vagrant.configure("2") do |config|
  # https://docs.vagrantup.com.

  config.vm.box = "ubuntu/xenial64"

  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"

  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    #apt-get upgrade
    apt-get install -y afl libtool htop scons gdb autoconf automake valgrind make cmake screen git vim linux-tools-common linux-tools-generic libini-config-dev
    apt-get autoremove

    curl http://lcamtuf.coredump.cx/afl/releases/afl-latest.tgz -o /opt/afl-latest.tgz
    cd /opt && tar -zxvf afl*
    cd afl-*
    make

    git clone https://github.com/droberson/thefuzz.git /opt/thefuzz

    git clone https://github.com/zardus/preeny.git /opt/preeny
    cd /opt/preeny
    make

    echo core >/proc/sys/kernel/core_pattern
    echo "echo core >/proc/sys/kernel/core_pattern" >>/etc/rc.local
  SHELL
end
