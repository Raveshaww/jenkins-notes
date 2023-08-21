# jenkins
Notes from learning Jenkins
### Prereqs
- What is CI/CD
    - CD as in delivery requires manual intervention to deploy
    - CD as in deployment just deploys without a human checking things
### Installing Jenkins
- Installing Jenkins in a VM
    - requires java
        - `sudo apt install openjdk-11-jdk`
    - add repo key
    - add to server source list 
    - systemctl start service
    - open firewall (`8080/tcp` by default)
        - to change the port, edit `/lib/systemd/system/jenkins.service `
    - unlock jenkins with the info from the file specified
- Jenkins CLI
    - You use ssh to communicate with the server