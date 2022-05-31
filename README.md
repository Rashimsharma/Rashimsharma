#######Steps to install Jenkins in Ubuntu 

Pre-requisites 

Step1: Install Java 
It is recommended that you install OpenJDK from the default repositories. Open a terminal window and enter the following:
  $ sudo apt update
  
Install OpenJDK 8 with:
  $ sudo apt install openjdk-8-jdk
  
Step 2: Add the Jenkins Repository
  A software repository is a server that holds software packages for download. Jenkins isn’t included in the default Ubuntu repositories, so you’ll need to add it.

   1. Start by importing the GPG key:

      $ curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
     
   2. Next, add the Jenkins software repository to the sources list and provide the key for authentication:

      $ echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

   The command adds the Long Term Support (LTS) stable release to the sources list.
   
Step 3: Install Jenkins
   1. To install Jenkins on Ubuntu, use the following commands:

   $  sudo apt update

   $ sudo apt install jenkins

   2. The system prompts you to confirm the download and installation. Press Y and hit Enter, and the system downloads and installs Jenkins.
   
   3. To check Jenkins was installed and is running enter:

   $ sudo systemctl status jenkins

 You should see a bright green entry that says active (exited). This means the service is running.
 
   4. Exit the status screen by pressing Ctrl+Z.

Step 4: Modify Firewall to Allow Jenkins
   You need to open Port 8080 to allow Jenkins to communicate.

   If you’re using the default UFW firewall, enter the following:

   $ sudo ufw allow 8080

   $ sudo ufw status
   
Step 5: Set up Jenkins
   1. To launch and set up Jenkins, open a web browser, and navigate to the IP address of your server:

   http://ip_address_or_domain:8080

   Use the actual IP address or domain name for the server you’re using Jenkins on. For example, if you're running locally, use:

   http://localhost:8080
   
   2. You should see a page that prompts you to Unlock Jenkins. You’ll need the default password. You can get the default password by switching to a command line and entering the following:

   $ sudo cat /var/lib/jenkins/secrets/initialAdminPassword

   3. The system returns an alphanumeric code. Enter that code, then click Continue.

   4. Next, you are prompted to either Install suggested plugins or Select plugins to install. It’s fine to simply install the suggested plugins.
   5. Then you will be prompted to Create First Admin User.
      Enter the credentials you want to use for your Jenkins administrator, then Save and Continue.

   6. After this, you should set up the Instance Configuration. This is the preferred network address for this Jenkins installation. Confirm the address you want to use for your server. This is most likely the same address you used to get to this configuration page. When you’re satisfied, click Save and Finish.

   7. You should see a page that says Jenkins is ready!


