# Ansible-Configuration-Management-Automate-Project-7-to-10-

## Step 1 - Install and Configure Ansible on EC2 Instance.

1. Update the Name tag on your Jenkins EC2 Instance to Jenkins-Ansible. We will use this server to run playbooks.

![image](https://github.com/user-attachments/assets/e455b81d-63c2-47f3-acad-bd1e2d8db77f)

2. In  GitHub account create a new repository and name it ansible-config-mgt.

![image](https://github.com/user-attachments/assets/f7b22390-4c02-47ce-982a-a3e79ea11c71)

3. Install Ansible.

```
sudo apt install ansible -y
```
![image](https://github.com/user-attachments/assets/c756167e-3da1-4f66-ad70-5407277e617d)

Check your Ansible version by running ansible --version

![image](https://github.com/user-attachments/assets/687138db-70b3-4d62-813c-4bebd0a99233)

4. Configure Jenkins build job to archive repository content every time you change it - this will solidify Jenkins configuration skills acquired in Project 9.

Create a new Freestyle project 'ansible' in Jenkins and point it to 'ansible-config-mgt' repository.

![image](https://github.com/user-attachments/assets/26f49128-5952-4977-98e3-38b4256ecdf0)

![image](https://github.com/user-attachments/assets/d328fd38-2b62-43a0-8621-030b2c4a16e8)

Configure a webhook in GitHub and set the webhook to trigger ansible build.

![image](https://github.com/user-attachments/assets/0e48274a-e5d8-4bbf-8b49-49d23c33e95d)

Configure a Post-build job to save all (**) files, like you did it in Project 9.
![image](https://github.com/user-attachments/assets/a5aabeab-7da0-4f48-8df5-4ad1e0a32ad6)

5. Test setup by making some change in README.md file in master branch and make sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder..

```
ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/
```

![image](https://github.com/user-attachments/assets/ff06f4b7-c2c7-411e-83db-4303eabbac20)
#### Note: Trigger Jenkins project execution only for main (or master) branch.

![image](https://github.com/user-attachments/assets/ff0ef5d0-039a-4a78-996d-5675d644c9e8)

Tip: Every time we stop/start.. Jenkins-Ansible server - you have to reconfigure GitHub webhook to a new IP address, in order to avoid it, it makes sense to allocate an Elastic IP to your Jenkins-Ansible server (we have done it before to your LB server in Project 10). Note that Elastic IP is free only when it is being allocated to an EC2 Instance, so do not forget to release Elastic IP once you terminate your EC2 Instance.

## Step 2 - Prepare your development environment using Visual Studio Code.

1. Installing the Visual Studio Code (VSC),
![image](https://github.com/user-attachments/assets/e2d7a049-6365-4e34-9894-5410df1e621e)

2. Clone down your ansible-config-mgt repo to your Jenkins-Ansible instance.

```
Clone down your ansible-config-mgt repo to your Jenkins-Ansible instance
```
![image](https://github.com/user-attachments/assets/3aa9e8f3-e37b-4b8b-ae14-a889657e5ae3)

## Step 3 - Begin Ansible Development.

1. In your ansible-config-mgt GitHub repository, create a new branch that will be used for development of a new feature.

Created the feature branch from main branch 'feature/ansible-1' 
![image](https://github.com/user-attachments/assets/c3793beb-871a-4b2a-9e39-1e5416a698b1)

To check the newly created branch locally.
```
git branch -r
```
![image](https://github.com/user-attachments/assets/a56b90d5-3888-4ceb-b985-ca645f475c53)


2. Checkout the newly created feature branch to  local machine and start building code and directory structure.

````
git checkout feature/ansible-1
git branch
````
![image](https://github.com/user-attachments/assets/09fbc74e-efb5-46c3-aada-f77a3186a9fd)

3. Create a directory and name it playbooks - it will be used to store all playbook files.

```
mkdir playbooks
```

4. Create a directory and name it inventory - it will be used to keep your hosts organised.

```
mkdir inventory
```
![image](https://github.com/user-attachments/assets/8f7f8c73-e5e2-438d-a5a8-e8b4c47ec0b4)

![image](https://github.com/user-attachments/assets/ee721f1b-34b7-4106-81d0-0a76d2e6509e)

5. Within the playbooks folder, create first playbook, and name it common.yml





![Uploading image.png…]()
