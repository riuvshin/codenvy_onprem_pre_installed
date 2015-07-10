box      = 'codenvy_onprem_3.10.3_preinstalled'
url      = 'https://install.codenvycorp.com/codenvy_onprem_3.10_preinstalled.box'
ram      = '3072'
hostname = 'onprem'
domain   = 'codenvy.com'
cpus     = '2'
bridge   = 'eth0'
 
puts "\033[32mCodenvy is now installed.\033[0m"
puts "\033[32mDNS: onprem.codenvy.com\033[0m"
puts "\033[32mAdmin Dashboard: onprem.codenvy.com/admin\033[0m"
puts "\033[32mAdmin user: admin\033[0m"
puts "\033[32mAdmin pass: password\033[0m"
 
Vagrant.configure("2") do |config|
  config.vm.box = box
  config.vm.box_url = url
  config.vm.host_name = hostname + '.' + domain
  config.vm.network :private_network, ip: "192.168.56.91"
 
config.vm.provider :virtualbox do |vbox|
    vbox.customize [
        'modifyvm', :id,
        '--name', hostname,
        '--memory', ram,
        '--cpus', cpus,
    ]
 end
end
