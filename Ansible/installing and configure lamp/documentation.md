### INSTALLING AND CONFIGURING ANSIBLE 
---
 
## Steps to proceed
---
* Create a two ubuntu vm's and one red-hat vm
* We will call one ubuntu vm as control node and other as node1 and node2
* Create devops user in all the vm's with sudo permission
![pic new](/IMAGES/ANSIBLE1.png)
* Now create a keypair in control node and copy the public key to other vm's
![pic new](/IMAGES/anisible2.jpg)
![alt text](/IMAGES/anisible3.jpg)

* Install Ansible on the control node
```
sudo apt update
sudo apt install software-properties-common -y
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible -y
```

![new txt](/IMAGES/anisible4.jpg)
* Now we can create a hosts file and add the private address in the hosts in the inventory
* Now we can connect to the nodes by giving the private ip address
![alt text](/IMAGES/ansible6.jpg)
we can see the ip address change
---
## INSTALL THE LAMP SERVER ON UBUNTU
---
* Now create two directory in devops user where the ansible is installed called in inventory and playbook
![alt text](/IMAGES/anisible7.jpg)
* In the inventory we have the hosts file in which we give the private ip address of our nodes
* In the playbook directory we write the playbook to the desired state for the machines present 
 ![alt text](/IMAGES/IMG-20230531-WA0045.jpg)
 * Now create the info.php file in the same folder as playbook same as below
 * Check connectivity by executing
  ```
   ansible -m ping -i hosts all
   ```

   ![alt text](/IMAGES/IMG-20230531-WA0036.jpg)
   *Now write the info.php 
   
 ![alt text](/IMAGES/IMG-20230531-WA0042.jpg)
 * NOW RUN THE COMMAND
  ```
  ansible-playbook -i <inventory-path> --syntax-check <playbook-path>
  ```
  ![alt text](/IMAGES/IMG-20230531-WA0047.jpg)
  * Now check the info.php by adding /info.php with the private ip address
  ![alt text](/IMAGES/IMG-20230531-WA0043.jpg)
