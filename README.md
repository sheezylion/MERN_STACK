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
As shown in the image below out index.js file is created

<img width="435" alt="20" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/974101a9-ce4c-4d29-be72-cc8b6b5612bb">

3. Install dotenv module with the command below:

```
npm install dotenv
```
<img width="480" alt="21" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/8cbb0b9c-d116-46da-822a-c89aed9d1d83">


4. Open index.js file using any text editor of your choice, in our case we would use the vim editor:

```
vim index.js
```

Type the code below into it

```
const express = require('express');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

app.use((req, res, next) => {
  res.header("Access-Control-Allow-Origin", "*");
  res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
  next();
});

app.use((req, res, next) => {
  res.send('Welcome to Express');
});

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```
The image below shows how the code you paste looks like in vim editor

<img width="757" alt="22" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/578f9aec-01ff-4f54-91fe-e8c1c412d754">

Note: Port 5000 have been specified to be used in the code. This will be required later on the browser.

5. Start the server to see if it works. Open your terminal in the same directory as your index.js file. Run the command below:

```
node index.js
```

Server is now running on port 5000 in the Terminal, as seen below: 

<img width="437" alt="23" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/de278d94-a9e0-49f7-85f8-d9c64577579e">

To open this server in our local browser, we need to do some settings in our EC2 instance security group by editing our inbound rules to open port 5000 as shown below:

<img width="1618" alt="24" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/69e13d4e-6284-4416-bef1-2cebdab69b44">

6. Access the server with the public IP followed by the port

```
100.26.35.141:5000
```
<img width="682" alt="25" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/80b4924a-54a6-4eb6-9c71-759c42c107b9">

### Routes
There are three actions that the ToDo application needs to be able to do:

- Create a new task
- Display list of all task
- Delete a completed task

Each task was associated with some particular endpoint and used different standard HTTP request methods: POST, GET, DELETE.

For each task, routes were created which defined various endpoints that the ToDo app depends on.

1. Create a folder routes, cd into the routes directory and create a file api.js inside the routes directory. We would use one command to achieve this using the && syntax:

```
mkdir routes && cd routes && touch api.js
```
<img width="609" alt="26" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/bbfae540-b809-43e8-95ad-96d6f8574685">

2. Open the api.js file using vim editor:

```
vim api.js
```

3. Copy the comman below inside api.js

```
const express = require('express');
const router = express.Router();

router.get('/todos', (req, res, next) => {

});

router.post('/todos', (req, res, next) => {

});

router.delete('/todos/:id', (req, res, next) => {

});

module.exports = router;
```
Next we would create models directory

#### Models
Models are defined using the schema interface. The schema allows you to define the fields stored in each document along with their validation requirements and default values. In essence, the schema is a blueprint of how the database will be constructed. In addition, you can define static and instance helper methods to make it easier to work with your data types, and also virtual properties that you can use like any other field, but which aren’t stored in the database.

To create a schema and a model, install Mongoose which is a Node package that makes working with MongoDB easier.

Change the directory back to Todo folder using cd .. command

```
cd ..
```

<img width="380" alt="27" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/659bb2b9-a1f2-40bb-8d84-4479b50dd419">

1. Now install mongoose, using npm command:

```
npm install mongoose
```

<img width="447" alt="28" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/d8dbba42-8d89-485e-a193-3c4cadb6ef19">

2. Create a new folder in your root directory and name it models. Cd inside the models directory and create a file, name it todo.js with the following code in it:

```
mkdir models && cd models && touch todo.js
```

<img width="596" alt="29" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/add56f00-19f1-4f45-8d88-2e8d51945f44">

3. Open the newly created file todo.js using vim text editor and pasted the following command

```
vim todo.js
```

```
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

// Create schema for todo
const TodoSchema = new Schema({
  action: {
    type: String,
    required: [true, 'The todo text field is required']
  }
});

// Create model for todo
const Todo = mongoose.model('todo', TodoSchema);

module.exports = Todo;
```
<img width="499" alt="30" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/609c19dd-acbd-457f-89d7-b9481bd96461">

Now, we need to update our routes to make use of the new model. In routes directory open api.js using vim and update with the following command. 

```
const express = require('express');
const router = express.Router();
const Todo = require('../models/todo');

router.get('/todos', (req, res, next) => {
  // This will return all the data, exposing only the id and action field to the client
  Todo.find({}, 'action')
    .then(data => res.json(data))
    .catch(next);
});

router.post('/todos', (req, res, next) => {
  if (req.body.action) {
    Todo.create(req.body)
      .then(data => res.json(data))
      .catch(next);
  } else {
    res.json({
      error: "The input field is empty"
    });
  }
});

router.delete('/todos/:id', (req, res, next) => {
  Todo.findOneAndDelete({"_id": req.params.id})
    .then(data => res.json(data))
    .catch(next);
});

module.exports = router;
```
<img width="736" alt="31" src="https://github.com/sheezylion/MERN_STACK/assets/142250556/764ef949-8024-4d2e-b378-18144a073240">



































