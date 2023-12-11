# How-to-Provision-a-Linux-EC2-Instance-Using-the-AWS-Management-Console
![image](https://github.com/Samuel-Kaniel/How-to-Provision-a-Linux-EC2-Instance-Using-the-AWS-Management-Console/assets/83005750/1ea31e2e-0cf0-4d26-a01a-59f367f147e2)

**Step-by-Step Guide**

### **Step 1: Sign in to the AWS Management Console**

Navigate to the AWS Management Console and log in with your credentials.

### **Step 2: Launching a New EC2 Instance**

1. In the AWS Management Console, select 'Services' and click on ‘EC2’ to open the EC2 Dashboard.
2. Click on the ‘Launch Instance’ button to start the instance setup process.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/4d8dc721-6314-45b3-bda3-e38472a716d3/Untitled.png)

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/af6db83d-07ca-4db7-b74f-50cda4121276/Untitled.png)

### **Step 3: Choose an Amazon Machine Image (AMI)**

1. Select the ‘Quick Start’ tab and choose the desired Linux AMI, such as Ubuntu Server 22.04 LTS, which is free tier eligible.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/540d51e4-89a2-414d-b08f-fb5182bb4eef/Untitled.png)
    

### **Step 4: Choose an Instance Type**

1. Choose an instance type that suits your needs. For example, you can select the 't2.micro' instance type for a free tier eligible option.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/64e14cc8-088f-473d-93cb-b0ed460cfa28/Untitled.png)
    

### **Step 5: Configure Instance Details**

Configure the instance to your requirements, including network and subnet configurations.

### **Step 6: Add Storage**

Accept the default storage device configuration or modify it according to your needs.

### **Step 7: Configure Security Group**

1. Set up a new security group or select an existing one.
2. Ensure that the security group has rules allowing SSH access.

### **Step 8: Review and Launch**

In the user data feature of EC2 to pass in a shell script to install NGINX. After that review your instance configuration and make any final adjustments. 

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/12e81172-f5e1-43d8-a7fe-55418c8fa8e5/Untitled.png)

### **Step 9: Create a Key Pair**

1. Before launching the instance, create a new key pair.
2. Enter a name for your key pair and download the private key file (.pem).
    
    ![Untitled (6).png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/22bb260e-a344-4f71-9dc6-97c9f2cab49c/Untitled_(6).png)
    

### 

### **Step 10: Connect to Your Instance**

1. Use the following SSH command, replacing 'your-key-name.pem' with the name of your key pair and 'public-dns-name' with the public DNS of your EC2 instance:
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/8a39a21e-43b5-4b4a-ac02-1ecb96b1d854/Untitled.png)
    

```

ssh -i /path/to/your-key-name.pem ubuntu@public-dns-name
```

It gives you an error messge just you don’t have permission to access. So you should change the file permission to only readable format using this command : “chmd 400 ~/Downloads/web.pem”

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/2137526e-2ec3-4a75-88c6-510da5a4fe16/0ea05aeb-49a3-48c8-8f70-0727dd600b32/Untitled.png)

## **Conclusion**

You have now successfully provisioned a Linux EC2 instance using the AWS Management Console and accessed it via SSH. This instance can serve as the foundation for various applications and services you wish to run in the cloud.
