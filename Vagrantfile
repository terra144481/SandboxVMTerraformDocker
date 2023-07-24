# Create environment Ubuntu22.04 + Docker + Terraform
# from turtorial  - https://developer.hashicorp.com/terraform/tutorials/certification-associate-tutorials-003/apply

HOSTNAME = "ubuntu"
MEMORY = 1024
CPUS = 2
DISK_SIZE = "40GB" 


# Create VM latest Ubuntu LTS image (Ubuntu 22.04 LTS)
# -----------------------------------------------------------------------------
Vagrant.configure("2") do |config|
    config.vagrant.plugins = ["vagrant-disksize"]
    config.vm.box = "ubuntu/jammy64"
    config.vm.box_version = "20230616.0.0"
    config.vm.hostname = HOSTNAME
    config.disksize.size = DISK_SIZE
    config.vm.network "public_network"
    config.vm.provider "virtualbox" do |v|
        v.name = "Ubuntu_terraform"
        v.memory = MEMORY
        v.cpus = CPUS            
      end

      # Install Terraform, Docker, jq      
# -----------------------------------------------------------------------------
    config.vm.provision "shell", path: "script.sh"     
    config.vm.provision "docker" do |d|
      d.pull_images "hello-world"         
    end
end

 

