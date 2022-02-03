# AWS-Deep-Thoughts
In this application, I refactored the existing MERN application Deep Thoughts, which allows users to sign up and create an account, post their thoughts, and share their thoughts and images with other users. I deployed this app to the cloud using AWS and replace the back-end API to use cloud resources for storage, database, and computing. To accomplish this, I configured a database service with DynamoDB, stored and retrieved static assets using S3, and deployed the app on an Ubuntu server to an EC2 instance.

# Introduction

I've explored not only full-stack web development and several front-end and back-end tech stacks, but also the inner workings of JavaScript execution, performant web applications, the internet itself, and much more.

I could easily stop there. But these days, the internet has become embedded in how we communicate, interact with, and find new customers, and for that reason, companies need more than just a website—they need a way to deliver that website to consumers consistently, reliably, and economically. While developing this application, I examined how cloud computing has solved this problem and caused a paradigm shift in how companies deliver web solutions to consumers.

I worked with an app that I've already built: the (Deep Thoughts)[ ] application, which allows users to post their thoughts. I built it using React, Node.js, Express.js, and MongoDB, which makes it a MERN application. Moving forward, I deploy this app to the cloud and replace the back-end API with cloud resources to handle the storage, database, and computing.

I chosen Amazon Web Services, or AWS, to fulfill this role. I chose AWS over other providers, like Microsoft Azure or the Google Cloud Platform, because AWS is currently the most comprehensive and widely adopted cloud platform. AWS offers the widest range of web services, a vast array of customers (from startups to enterprise), and an extensive free tier.

# Tools I Used

- [AWS](https://aws.amazon.com/), also known as Amazon Web Services, is currently the most comprehensive and widely used cloud computing platform, providing on-demand services to a vast array of customers—including individuals, companies, and governments and ranging from startup to enterprise. Offered on a pay-as-you-go basis, AWS includes an extensive free service tier, which I useed for this application. Signing up did require a credit card, but I wasn't be charged any fees to create the application.

    ### I used the following AWS resources in this application:
     - [IAM](https://aws.amazon.com/iam/), or Identity and Access Management, helps ensure secure access to AWS services and resources. The IAM user console enables you to create and manage AWS users and groups as well as allow and deny access to AWS resources.

     - [S3](https://aws.amazon.com/s3/), or Simple Storage Service, is an object storage service used by companies of all sizes and in all industries. S3 allows customers to store and protect any amount of data for various uses, ranging from web and mobile applications to data archives and hybrid cloud storage. For this application, I used it to store and retrieve static assets for my application.

     - [DynamoDB](https://aws.amazon.com/dynamodb/) is a NoSQL key-value and document database that delivers incredibly fast performance—no matter the size of your data. This fully managed and multi-region database provides built-in security, backup, and in-memory caching for web applications. I used DynamoDB as the database for my application.

     - [EC2](https://aws.amazon.com/ec2/), or Elastic Compute Cloud, is a secure, scalable web service designed to simplify cloud computing. As the name suggests, EC2 offers flexibility when you need to obtain and configure capacity for your web applications. I used EC2 to configure a Linux server to host my application.

- The [AWS Command Line Interface](https://aws.amazon.com/cli/), or AWS CLI, helped me bring together my various AWS services, by controlling them from the command line. I could also automate these services by using scripts.

- I used the following npm packages in this course:

    - [aws-sdk](https://www.npmjs.com/package/aws-sdk) is the official AWS software development kit (SDK) for JavaScript. Available for browsers, mobile devices, or Node.js back ends, this package allowed my Node.js application to interface with AWS.

    - [multer](https://www.npmjs.com/package/multer) is a Node.js middleware for handling file uploads. In this project, I used it as a container for image files until they were ready to be uploaded to an S3 bucket.

    - [uuid](https://www.npmjs.com/package/uuid) stands for universally unique identifier. This package generates random alphanumeric strings that can serve as unique identifiers. I used this package to generate identifiers for my S3 bucket and for my application’s images.

    - [pm2](https://www.npmjs.com/package/pm2) is a Node.js production process manager that helped me manage my web application—and keep it live online. I used this package to keep my application running even after logging out of the server on EC2.

- [nginx](https://www.nginx.com/), sometimes stylized as NGINX or NginX, is a free and open-source web server that can also serve as a reverse proxy, load balancer, mail proxy, or HTTP cache. I used it as an application server to expose the EC2 instance to the internet.

# Cloud Computing and AWS

All modern web applications revolve around data. With an ever-increasing number of users, many businesses and individuals struggle to maintain important information, programs, and systems on internal computer servers. Cloud computing offers a solution to this challenge, providing on-demand computer system resources like applications, data storage, and processing power—all typically delivered over the internet on a pay-as-you-go basis, and requiring no direct active management by the user.

The cloud is just another word for resources that are stored remotely on the internet. Whereas anything stored or saved directly on your computer is stored locally, anything that you access through an online, remote service is said to be stored in the cloud. Of course, these resources are actually stored on physical servers that users access through online services.

Cloud computing has been around since the late 90s, but its popularity has skyrocketed as data usage has grown. For example, you are probably already familiar with web-based email, such as Gmail, Hotmail, or Yahoo Mail, where users’ emails are stored on servers rather than their computers. This means that the user can check their email from any device with access to the internet. Other common examples include video streaming (Netflix, Prime Video, Hulu), file storage (Dropbox, Google Drive, iCloud), file sharing (Google Docs), and online backup (Carbonite).

These examples of cloud computing largely pertain to personal use, but what about companies that need to access large amounts of data over a secure online network connection? Cloud solutions that tailor their services to companies frequently follow the <strong>aaS</strong> (as a service) architecture, with three primary models: infrastructure as a service <strong>(IaaS)</strong>, platform as a service <strong>(PaaS)</strong>, and software as a service <strong>(SaaS)</strong>. You don’t need to know the specifics of each of these models—just that the companies using them no longer have to set up infrastructure, install a platform, or install software on their local machines. Instead, they access the services through the internet.

Amazon Web Services, commonly known as AWS, is currently the most comprehensive and widely adopted cloud platform. It boasts the largest offering of web services, a vast array of customers ranging from startups to enterprise, and an extensive free tier of services.
