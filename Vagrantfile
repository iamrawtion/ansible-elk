# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "echo Hello"

  $num_instances = 3
  (1..$num_instances).each do |i|
    config.vm.define "elastic#{i}" do |elastic|
      elastic.vm.box = "ubuntu/trusty64"
      elastic.vm.box_url = "ubuntu/trusty64"
      elastic.vm.network :private_network, ip: "192.168.1.#{i+110}"
      elastic.vm.provider :virtualbox do |v|
        v.memory = "2048"
        v.cpus = 1
        v.name = "elastic#{i}"
      end
    end
  end

  $num_instances = 1
  (1..$num_instances).each do |i|
    config.vm.define "logstash#{i}" do |logstash|
      logstash.vm.box = "ubuntu/trusty64"
      logstash.vm.box_url = "ubuntu/trusty64"
      logstash.vm.network :private_network, ip: "192.168.1.#{i+120}"
      logstash.vm.provider :virtualbox do |v|
        v.memory = "2048"
        v.cpus = 1
        v.name = "logstash#{i}"
      end
    end
  end

  config.vm.define "kibana" do |kibana|
    kibana.vm.box = "ubuntu/trusty64"
    kibana.vm.box_url = "ubuntu/trusty64"
    kibana.vm.network :private_network, ip: "192.168.1.150"

    kibana.vm.provider :virtualbox do |v|
        v.memory = "512"
        v.cpus = 1
        v.name = "kibana"
    end
  end

  $num_instances = 1
  (1..$num_instances).each do |i|
    config.vm.define "kafka#{i}" do |kafka|
      kafka.vm.box = "ubuntu/trusty64"
      kafka.vm.box_url = "ubuntu/trusty64"
      kafka.vm.network :private_network, ip: "192.168.1.#{i+130}"
      kafka.vm.provider :virtualbox do |v|
        v.memory = "2048"
        v.cpus = 1
        v.name = "kafka#{i}"
      end
    end
  end

end
