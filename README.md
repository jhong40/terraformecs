"# terraformecs" 
provisioner "remote-exec" {
     script = "scripts/wait_for_instance.sh"
}

provisioner "local-exec" {
  command = "ansible-playbook ..."
}


#!/bin/bash

while [ ! -f /var/lib/cloud/instance/boot-finished ]; do
  echo -e "\033[1;36mWaiting for cloud-init..."
  sleep 1
done
