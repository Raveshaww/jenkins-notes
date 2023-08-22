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
### Jenkins Plugins and Integrations
- Searching through plugins
    - located in `manage jenkins` section
- Jenkins steps and plugin
    - Example of installing with cli:
        - `java -jar jenkins-cli.jar -s http://localhost:8085 -auth 'admin:Adm!n321' install-plugin cloudbees-bitbucket-branch-source`
### Jenkins Ui
- managing users and teams
    - if you wanna do a role based implementation, you have to install a plugin
### Systems Administration with Jenkins
- backup
    - backup `jenkins_home` directory
        - this contains:
            - jobs (aka pipelines)
            - config
    - you can do filesystem snapshots, use a plugin, or just write a shell script to back up the instance
- restore
    - copy the files back!
### Pipelines
- build a pipeline
    - example pipeline in `jenkinsfile_examples/Jenkinsfile`
    - by default, completed builds are stored here:
        - `/var/lib/jenkins/workspace`
            - the build will be the name of the pipeline