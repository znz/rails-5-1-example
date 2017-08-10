Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.provision "shell", inline: <<-'SH'
export DEBIAN_FRONTEND=noninteractive
apt-get update
apt-get dist-upgrade -y
apt-get install -y bundler
apt-get install -y postgresql
apt-get install -y libpq-dev libxslt1-dev zlib1g-dev
#apt-get install -y nodejs
su - postgres -c 'createuser vagrant' || :
su - postgres -c 'createdb rails-5-1-example_development' || :
  SH
end
