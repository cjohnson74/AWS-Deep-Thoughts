# AWS-Deep-Thoughts
In this application, I refactored the existing MERN application Deep Thoughts, which allows users to sign up and create an account, post their thoughts, and share their thoughts and images with other users. I deployed this app to the cloud using AWS and replace the back-end API to use cloud resources for storage, database, and computing. To accomplish this, I configured a database service with DynamoDB, stored and retrieved static assets using S3, and deployed the app on an Ubuntu server to an EC2 instance.

# Tools I Used

- [AWS](https://aws.amazon.com/), also known as Amazon Web Services, is currently the most comprehensive and widely used cloud computing platform, providing on-demand services to a vast array of customers—including individuals, companies, and governments and ranging from startup to enterprise. Offered on a pay-as-you-go basis, AWS includes an extensive free service tier, which I useed for this application. Signing up did require a credit card, but I wasn't be charged any fees to create the application.

    ### I used the following AWS resources in this application:
     - [IAM](https://aws.amazon.com/iam/), or Identity and Access Management, helps ensure secure access to AWS services and resources. The IAM user console enables you to create and manage AWS users and groups as well as allow and deny access to AWS resources.

     - [S3](https://aws.amazon.com/s3/), or Simple Storage Service, is an object storage service used by companies of all sizes and in all industries. S3 allows customers to store and protect any amount of data for various uses, ranging from web and mobile applications to data archives and hybrid cloud storage. For this application, I used it to store and retrieve static assets for my application.

     - [DynamoDB](https://aws.amazon.com/dynamodb/) is a NoSQL key-value and document database that delivers incredibly fast performance—no matter the size of your data. This fully managed and multi-region database provides built-in security, backup, and in-memory caching for web applications. I used DynamoDB as the database for my application.

     - [EC2](https://aws.amazon.com/ec2/), or Elastic Compute Cloud, is a secure, scalable web service designed to simplify cloud computing. As the name suggests, EC2 offers flexibility when you need to obtain and configure capacity for your web applications. I used EC2 to configure a Linux server to host my application.

- The (AWS Command Line Interface)[https://aws.amazon.com/cli/], or AWS CLI, helped me bring together my various AWS services, by controlling them from the command line. I could also automate these services by using scripts.

- I used the following npm packages in this course:

    - [aws-sdk](https://www.npmjs.com/package/aws-sdk) is the official AWS software development kit (SDK) for JavaScript. Available for browsers, mobile devices, or Node.js back ends, this package will allow your Node.js application to interface with AWS.

    - [multer](https://www.npmjs.com/package/multer) is a Node.js middleware for handling file uploads. In this project, you’ll use it as a container for image files until they’re ready to be uploaded to an S3 bucket.

    - [uuid](https://www.npmjs.com/package/uuid) stands for universally unique identifier. This package generates random alphanumeric strings that can serve as unique identifiers. You’ll use this package to generate identifiers for your S3 bucket and for your application’s images.

    - [pm2](https://www.npmjs.com/package/pm2) is a Node.js production process manager that helps you manage your web application—and keep it live online. You’ll use this package to keep your application running even after you’ve logged out of the server on EC2.

- [nginx](https://www.nginx.com/), sometimes stylized as NGINX or NginX, is a free and open-source web server that can also serve as a reverse proxy, load balancer, mail proxy, or HTTP cache. You’ll use it as an application server to expose the EC2 instance to the internet.
