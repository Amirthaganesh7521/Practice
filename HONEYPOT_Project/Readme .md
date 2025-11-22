in this repo  tells to  develop the basic honeypot setup  by cowrie  

#    Install and Configure Cowrie

### 1. Download updated package lists.
    sudo apt-get update
 
### 2. Install Cowrie’s dependencies.    

    sudo apt-get install python3.git virtualenv libmpfr-dev libssl-dev libmpc-dev libffi-dev build-essential libpython-dev python-pip

### 3. Add a new user named, cowrie.

    sudo adduser — disabled-password cowrie

### 4. Navigate to the home directory of user, cowrie, and clone the cowrie git repository.

    git clone https://github.com/micheloosterhof/cowrie.git

<img width="720" height="113" alt="image" src="https://github.com/user-attachments/assets/d8faa94f-9dd2-45f7-a9d1-2b58c950a73a" />


### 5. Create a new Python virtual environment for cowrie.

     cd cowrie
     virtualenv cowrie-env

###  Activate the virtual environment.
    source cowrie-env/bin/activate

### The terminal will display (cowrie-env) before the username, cowrie.

### Install pycrypto, Crypto and other requirements.

    pip install pycrypto Crypto
    (cowrie-env)$ pip install -r requirements.txt

### Generate a key for the cowrie instance.
    cd data
    ssh-keygen -t dsa -b 1024 -f ssh_host_dsa_key
    cd ..
    export PYTHONPATH=/home/cowrie/cowrie


#  Additional Cowrie Configuration


### Make a copy of the config file for your new cowrie instance.
     cd /home/cowrie/cowrie/ 
     cp cowrie.cfg.dist cowrie.cfg
     vi ./cowrie.cfg

### Set the hostname in the configuration file to a server name of your choice. E.g. fileserver4

    <img width="1400" height="1034" alt="image" src="https://github.com/user-attachments/assets/f65c7aeb-f162-4906-89b2-6dfc3fb92bac" />

### Change the Port to listen for incoming SSH connections to port 22.  and Write your changes and quit vi.
      Ctrl + C
     :wq

     
### Enable authbind in cowrie’s start.sh file.

     sudo vi /home/cowrie/cowrie/start.sh
Change line 2 to read:

AUTHBIND_ENABLED=yes

  <img width="720" height="371" alt="image" src="https://github.com/user-attachments/assets/c6a35102-740c-4439-b819-46a16ef0bcf3" />


          sudo apt-get install authbind
          sudo touch /etc/authbind/byport/22
          sudo chown cowrie /etc/authbind/byport/22
          sudo chmod 777 /etc/authbind/byport/22

### Start Cowrie
Execute the following commands to start Cowrie.

         sudo su cowrie
         cd /home/cowrie/cowrie/
         source cowrie-env/bin/activate
         ./start.sh
  <img width="720" height="203" alt="image" src="https://github.com/user-attachments/assets/d3f142c5-dece-427c-8712-e158a9ca2512" />


### Verify cowrie is listening on port 22 by running the command below.

      netstat -tan
    
  
  <img width="720" height="64" alt="image" src="https://github.com/user-attachments/assets/951bb9ac-8af9-4b24-a91b-d6878d7f5e34" />

### Execute the following command to start the SSH service.

      sudo /etc/init.d/ssh start

### the following command to stop Cowrie.

         ./stop.sh

#### Review the Cowrie Log File
- Connect to your server (not the Cowrie instance) and review the log file.

        cat /home/cowrie/cowrie/log/cowrie.log | less
   
### The attacker’s IP address will be shown in the red areas in the image below.

<img width="720" height="181" alt="image" src="https://github.com/user-attachments/assets/d0746770-0376-4649-8381-734b89cb5edb" />


