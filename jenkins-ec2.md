# Setting Up Jenkins of AWS EC-2

### 1. Setting up EC-2   
Created AWS `EC-2` with `Ubuntu-22.04` OS having public IP.

![ec-2](images/ec2.png)


### 2. Updating System   
Before starting the installation of jenkins, it is recommend that we update our Ubuntu packages available. We can do so by using the update command:    
```bash
sudo apt update
```

### 3. Installing JAVA OpenJDK   
Jenkins requires the Java Runtime Environment (JRE) for operation. So We’ll use OpenJDK to set up the Java environment for this guide. The OpenJDK development kit includes JRE.   

```bash
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
```


### 4. Installing Jenkins       

Following is script to install on debian/ubuntu based linux as per [Jenkins.io](https://www.jenkins.io/doc/book/installing/linux/#debianubuntu).    
```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

Enabling , Starting & Checking status of Jenkins.   

```bash
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
```

Opening Jenkis web interface.

` <ec2-public-ip>:8080`

