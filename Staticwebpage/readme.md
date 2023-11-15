# AWS EC2 Static Web Page Project

Welcome to the AWS EC2 Static Web Page Project! This project demonstrates how to deploy a simple static web page on an Amazon EC2 instance, take a snapshot of the instance's disk, and restore the project by launching a new EC2 instance from the snapshot.

## Project Overview

This project includes the following steps:

1. Create an EC2 instance on AWS.
2. Install a web server and host a "Hello World" static web page.
3. Take a snapshot of the EC2 instance's disk for backup.
4. Delete the original EC2 instance.
5. Deploy a new EC2 instance from the snapshot, showcasing disk backup and restore.

## Installation Instructions

### Step 1: Set Up Your EC2 Instance

1. Create an EC2 instance on AWS using the provided key pair.
2. Connect to your EC2 instance using EC2 Instance Connect or SSH.

```bash
ssh -i your-key-pair.pem ec2-user@your-ec2-public-ip
```

3. Install a web server (Apache) and start it.

```bash
sudo yum update -y
sudo yum install httpd -y
sudo service httpd start
```

4. Create a simple HTML page in the `/var/www/html` directory.

```bash
echo "<h1>Hello World</h1>" | sudo tee /var/www/html/index.html
```

5. Access the web page using your EC2 instance's public IP address.

### Step 2: Take a Snapshot of the EC2 Instance

1. Navigate to the EC2 service in the AWS Management Console.
2. Under "Elastic Block Store," select "Snapshots."
3. Find the volume associated with your EC2 instance and create a snapshot.

## Usage

After completing the installation instructions, you can access the "Hello World" web page by navigating to your EC2 instance's public IP address in a web browser.

## Project Structure

- `/var/www/html`: Directory containing the hosted HTML file.

## Screenshots

![Alt text](<./images/Screenshot%20(101).png>)

![Alt text](<./images/Screenshot%20(102).png>)

![Alt text](<./images/Screenshot%20(104).png>>)

![Alt text](<./images/Screenshot%20(105).png>)

![Alt text](<./images/Screenshot%20(107).png>)

![Alt text](<./images/Screenshot%20(109).png>)

![Alt text](<./images/Screenshot%20(113).png>)

![Alt text](<./images/Screenshot%20(114).png>)

![Alt text](<./images/Screenshot%20(116).png>)

![Alt text](<./images/Screenshot%20(122).png>)

![Alt text](<./images/Screenshot%20(123).png>)

## Issues or Troubleshooting

### Issue: Web Page Not Accessible After Launching EC2 Instance

#### Problem Description

After launching the EC2 instance with my custom AMI, I encountered an issue where the web page was not accessible even though the security group rules appeared to be configured correctly.

#### Troubleshooting Steps

1. **Checked Security Group Rules:**

   - Verified that the security group associated with the EC2 instance allowed inbound traffic on port 80 (HTTP).

2. **Examined Instance State:**

   - Ensured that the EC2 instance was in the "running" state.

3. **Verified Web Server Status:**

   - Connected to the instance using EC2 Instance Connect and checked the status of the web server (httpd).

     ```bash
     sudo service httpd status
     ```

     Discovered that the web server was not running.

4. **Started Web Server:**

   - Started the web server:

     ```bash
     sudo service httpd start
     ```

#### Resolution

After starting the httpd service, the web page became accessible, and the issue was resolved.

## Acknowledgments

- [Amazon Web Services (AWS)](https://aws.amazon.com/) for providing the cloud infrastructure.
- [Markdown Guide](https://www.markdownguide.org/) for Markdown syntax reference.

```

```
