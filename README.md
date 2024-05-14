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



