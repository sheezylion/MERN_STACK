# MERN WEB STACK IMPLEMENTATION IN AWS

![MERN-Stack](https://github.com/sheezylion/MERN_STACK/assets/142250556/0abede56-e038-4b3b-bc1e-ea87adf9d57e)

## What is MERN Stack?
MERN stack is a collection of technologies that enables faster application development. 
It is used by developers worldwide. The main purpose of using MERN stack is to develop apps using JavaScript only. 
This is because the four technologies that make up the technology stack are all JS-based. Thus, if one knows JavaScript (and JSON), the backend, frontend, and database can be operated easily. 

## MERN Stack Full Form
MERN Stack is a compilation of four different technologies that work together to develop dynamic web apps and websites. 

It is a contraction for four different technologies as mentioned below:

- M - MongoDB
- E - ExpressJS
- R - ReactJS
- N - NodeJS

## MERN Stack Components
There are four components of the MERN stack. Let’s discuss each of them one by one. 

- The first component is MongoDB, which is a NoSQL database management system. 
- The second MERN stack component is ExpressJS. It is a backend web application framework for NodeJS.
- The third component is ReactJS, a JavaScript library for developing UIs based on UI components. 
- The final component of the MERN stack is NodeJS. It is a JS runtime environment, i.e., it enables running JavaScript code outside the browser.

### Prerequisites
Have an AWS account set up and have an Admin user created with full admin permissions.

#### Step 1: Launch a Virtual Server with Ubuntu Server OS

##### Sign in to the AWS Management Console
To get started, sign in to the AWS Management Console using your AWS account credentials. If you don’t have an AWS account, you can create one easily by following the instructions on the AWS website.

##### Open the EC2 Console Once you are signed in to the AWS Management Console
Search for “EC2” in the services search bar and click on “EC2” from the search results. This will open the EC2 console, where you can manage your instances.

<img width="883" alt="1" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/f4fadaee-616d-45d4-92bc-60022825c468">

##### Launch Instance
In the EC2 console, click on the “Launch Instance” button to start the instance creation process. This will take you through a series of steps to configure your instance.
After clicking on the “Launch Instance” button, you will be redirected to a page as shown below.

<img width="895" alt="2" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/7507b539-a01c-4634-bfbe-37dabe92f226">

##### Provide a Name for the EC2 Instance
You need to provide a name for your EC2 instance. Giving your instance a meaningful name can help with easy identification and management of your resources in the future.
In this case, we enter enter “mern_server” as the name for our EC2 server.

<img width="799" alt="3" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/bb4e21ff-e9c7-4ba5-b1c1-3724a84e24e5">

##### Choose an Amazon Machine Image (AMI)
An Amazon Machine Image (AMI) is a pre-configured template that contains the operating system and other software necessary for your instance. In this step, you can choose from a wide variety of AMIs provided by AWS or the AWS Marketplace. Select an AMI that best suits your requirements.
In this case, we choose “Ubuntu server” as the operating system for your instance.

<img width="734" alt="4" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/f2197b17-6e37-4182-8b48-5b5cd1298b74">

##### Choose an Instance Type
The instance type determines the hardware of the host computer used for your instance. AWS offers a range of instance types with varying compute, memory, and storage capabilities. Consider your workload requirements and select the instance type that meets your needs.
In this case, you can select “t2.micro” as the instance type. The “t2.micro” instance type is eligible for the AWS Free Tier, which provides limited free usage of certain AWS services.

<img width="739" alt="5" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/e0e0e858-ec6e-47d1-88b9-3af095c53f93">

##### Create a Key Pair
To securely access your EC2 instance from your system, you need to create a key pair. A key pair consists of a public key that AWS stores and a private key that you download to your local machine. The private key is used to authenticate and establish a secure connection with your EC2 instance.

You have the option to select an existing key pair if you already have one, or you can create a new key pair by clicking on the “Create new key pair” button. I already have an existing key pair created

<img width="730" alt="6" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/9606d1f5-f19d-42f9-9acf-4e5965fb06d5">

##### Configure Instance Details, Add Storage, and Configure Security Groups
In this step, you can configure various settings for your EC2 instance. Adjust these settings based on your specific requirements. You have the flexibility to update these details even after launching the instance.

- Instance Details: Configure settings such as the number of instances to launch and network settings. You can specify the desired number of instances, choose the VPC (Virtual Private Cloud) network, and assign an IAM (Identity and Access Management) role if needed. You can also enable detailed monitoring for enhanced metrics on your instance’s performance.
- Storage: Specify the amount and type of storage to attach to your instance. AWS provides Elastic Block Store (EBS) volumes for persistent storage. Consider factors such as storage size, performance requirements, and encryption options. You can configure storage options according to your needs.

Remember, these configuration details can be updated later after launching the instance. You can leave them as they are for now and make changes as necessary in the future.

On the right side of the EC2 instance launch page, you will find the summary details section. This section provides a consolidated view of the configuration settings you have chosen for your instance. It allows you to review and verify the settings before launching the instance.

<img width="730" alt="7" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/814aad15-ebe9-4c69-98e2-1ec01d4f9ece">

##### Review and Launch
Before launching the instance, review the configuration details to ensure everything is set up correctly. Double-check the instance type, storage options, security groups, and any additional settings you have configured. If everything looks good, click on the “Launch Instance” button.

After launching the instance, you will be redirected to a page displaying a success dialogue box. To view the list of instances, click on the instance ID. In mycase, the instance ID is “i-0b631b7f55cae146a” as shown below.

<img width="797" alt="8" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/19c16060-e8b2-4dfa-a234-2918e449791e">

Clicking on the instance ID will take you to the EC2 Instances page, where you can see the details and manage your instances effectively.

<img width="1391" alt="9" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/5bb90a33-9005-4b80-abb7-3a2b65c0a4c7">

This page provides comprehensive information about our instances, including status, instance type, public IP address, and other relevant details. 

##### Connect to Instance
I will connect to this using ssh client via port 22. This is done using the following block of code:

```
ssh -i keypair.pem ubuntu@100.26.35.141
```

<img width="717" alt="10" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/51028061-a5c9-4738-bb91-9564621e8e9f">

#### Step 2: Backend Configuration
Remember the first step in this project we set up an Ubuntu server on AWS. In order to proceed, we will connect to this server and configure the backend components. Then we will install NodeJS, npm, create a directory called “Todo” to store files for this project, and then use the npm init command to generate a new file in this “Todo” directory that contains information about the application and the dependencies that it needs to run.

NPM is a package manager for Node, like apt for Ubuntu, it is used to install Node modules and packages and to manage dependency conflicts. But first we need to update and upgrade the ubuntu server:

```
sudo apt update
sudo apt upgrade
```

To get the location of Node.js software from ubuntu repository, type the following command into your terminal:

```
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

<img width="977" alt="Screenshot 2024-05-14 at 16 58 52" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/07d689e0-9ae3-4a18-ba78-5308f7ba627d">

#### Install Node.js on the server
Install node.js with the command below

```
sudo apt-get install -y nodejs
```

<img width="816" alt="12" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/0e46b645-3246-4c2a-8fd2-44980304d69e">

Note: By default the comman above has installed both node.js and npm. NPM is a package manager for node, same as how apt is a package manager for ubuntu.

We can verify the node installation with the comman below:

```
node -v
```
<img width="296" alt="13" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/2559054d-f852-46f2-af6f-2b89284a40e2">
We can also verify npm installation with the comman below:

```
npm -v
```
<img width="316" alt="14" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/4561f530-e93e-4e4d-addf-31960162c491">

#### Application code setup

We would create a new directory for our TO-DO project using the mkdir command 

```
mkdir Todo
```
Run the ls command below to verify if the TOdo directory has been created

```
ls
```

<img width="280" alt="15" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/a698ef88-99b3-499e-b170-0b509af7e13a">

Note: To see a well detailed information of the Todo directory created you can use addition comman with ls. example ls -lih. You can also type "man ls". Man means manual which is used to view more details on how to use the ls command.

Next, change your directory to the newly created one using the cd command below:

```
cd Todo
```

<img width="380" alt="16" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/6f1c5834-c32d-43f9-b070-44f9405c7efb">

Next, we will use the npm init command to initialize our project, where a new file package.json will be created. The package.json  contains information about our apllication and its dependencies that it needs to run.

```
npm init
```
Note: Follow the prompts after running the command. You can press enter several times to accept default values,
then accept to write out the package.json file by typing yes just like the image below:

<img width="814" alt="17" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/76cb6130-ef4d-47e0-9c5f-d6e24a080890">

Run the command ls to confirm if you have the package.json file created in your todo directory

```
ls
```
<img width="469" alt="18" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/48d08e82-a05c-417d-8e34-07bea8264100">

Next we will install expressjs and create the routes directory

#### Install expressJs 
ExpressJs is a framework for Node.js. Hence it simplifies development and abstracts a lot of low level details. For example, express helps to define routes of your application based on HTTP methods and URLs.

1. Install express by using npm command:

```
npm install express
```
<img width="479" alt="19" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/496e9a6b-101a-4216-b391-3a55031a2523">

2. Next create a file named "index.js" using the command below. We used 2 commands which is touch and ls. Touch is used to create a file and ls is used to list out the files created. The && command is used to input two commands at the same time

```
touch index.js && ls
```
As showmn in the image below out index.js file is created

<img width="435" alt="20" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/974101a9-ce4c-4d29-be72-cc8b6b5612bb">



















