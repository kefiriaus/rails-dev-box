# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box      = 'ubuntu/trusty64' # 14.04
  config.vm.hostname = 'rails-dev-box'

  # For Mac
  config.vm.synced_folder '/Users/kefiriaus/RubymineProjects', '/vagrant', type: 'rsync'

  # For Windows
  # config.vm.synced_folder 'C:\\Users\\kefiriaus\\RubymineProjects', '/vagrant', type: 'rsync'

  config.vm.network :forwarded_port, guest: 3000, host: 3333
  config.vm.network :forwarded_port, guest: 80, host: 3380
  config.vm.network :forwarded_port, guest: 443, host: 3443

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true

  config.vm.provider 'virtualbox' do |v|
    v.memory = 1024
    v.cpus = 2
  end
end
