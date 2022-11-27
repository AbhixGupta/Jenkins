# Jenkins

Jenkins is a Java-based open-source automation tool with built-in continuous integration plugins. Jenkins is used to continuously build and test your software projects, making it simpler for developers to incorporate changes to the project and for users to get a new build. By integrating with a wide range of testing and deployment technologies, it also enables you to deliver your software continuously.

Organizations can use Jenkins to automate and speed up the software development process. Jenkins combines all stages of the development lifecycle, including build, document, test, package, stage, deploy, static analysis, and many others.

Plugins assist Jenkins in achieving Continuous Integration. DevOps stages can be integrated thanks to plugins. Installing the utility's plugins is necessary if you want to incorporate that tool. Git, Maven 2 projects, Amazon EC2, HTML publishers, etc. are a few examples.

### Use Case:

- Automates the pipeline setup with Jenkinsfile.
- Jenkinsfile define stages in CI/CD pipeline.
- Jenkinsfile is a text file with pipeline DSL Syntax.
- There are two ways to define syntax:
  - Syntax
  - Declarative

#### Example

```bash
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                //
            }
        }
        stage('Test') {
            steps {
                //
            }
        }
        stage('Deploy') {
            steps {
                //
            }
        }
    }
}
```

## Jenkins Installation:

#### Prerequisite

- Java, JRE, JDK
- Any Operating System

#### Steps

1. Login into the AWS EC2 console and launch one Linux mahcine (ubuntu or red hat). Make sure to add seperate security group which have ssh enabled on port 22 with source is your Ip. Add Custom TCP port enabled on 8080 with source is your Ip.
2. Add Tags.
3. Create Key-Pairs.
4. Login to the Jenkins server (can use Putty, MobaXterm, terminal).

```bash
ssh -i /Downloads/jenk.pem ubuntu@145.45.45.6
```

4. Install the required configuration

```bash
sudo add-apt repository ppa:openjdk -r/ppa
sudo apt update
sudo apt install openjdk-8-jdk -y
```

5. Go to the Jenkins [website](https://www.jenkins.io/doc/book/installing/linux/) and see the latest installation steps according to your operating system.

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

6. Run the follwing commands

```bash
systemctl status jenkins
systemctl is-enabled jenkins
ps -ef | grep jenkins
ss -tunpl | grep 8080
```

Copy the Pulic Ip and paste in Browser with "IP:8080" and setup the rest jenkins according to your need.
