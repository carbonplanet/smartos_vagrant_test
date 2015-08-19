Vagrant.configure('2') do |config|
  config.vm.provider 'virtualbox' do |v|
    v.memory = 2048
  end

  # See https://vagrantcloud.com/livinginthepast for SmartOS boxes
  config.vm.box = 'livinginthepast/smartos-base64'
  config.vm.synced_folder '.', '/vagrant', type: "rsync", disabled: false
  config.vm.communicator = 'smartos'

  config.ssh.insert_key = false

  config.global_zone.platform_image = 'latest'

  config.zone.name = 'base64'
  config.zone.brand = 'joyent'
  config.zone.image = 'd34c301e-10c3-11e4-9b79-5f67ca448df0'
  config.zone.memory = 1536
  config.zone.disk_size = 5
end

