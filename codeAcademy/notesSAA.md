AWS Solutions Architect Associate 2022: Data Storage Services
AWS provides various storage services, including databases, Elastic Compute Cloud (EC2) instance volumes and the ability to import large data sets from on-premises into the AWS cloud. In this course, discover how AWS Transfer and Snow Family services support importing data to the AWS cloud over the Internet and by shipping storage devices to AWS data centers. Then, plan database usage in accordance with anticipated workloads. Next, deploy and manage various database solutions such as MySQL, Microsoft SQL Server, DynamoDB and DocumentDB. Lastly, create and attach a WEB volume and configure an Elastic File System (EFS). This course can be used to prepare for exam SAA-C03, AWS Certified Solutions Architect - Associate.
Table of Contents
    1. Video: Course Overview (it_clasaa22_02_enus_01)

    2. Video: Using AWS Transfer (it_clasaa22_02_enus_02)

    3. Video: AWS Snow Family (it_clasaa22_02_enus_03)

    4. Video: Creating an AWS Snow Family Job (it_clasaa22_02_enus_04)

    5. Video: AWS Database Capacity Planning (it_clasaa22_02_enus_05)

    6. Video: Deploying MySQL Using the Console (it_clasaa22_02_enus_06)

    7. Video: Managing MySQL in AWS (it_clasaa22_02_enus_07)

    8. Video: Deploying Microsoft SQL Server in AWS (it_clasaa22_02_enus_08)

    9. Video: Managing Microsoft SQL Server (it_clasaa22_02_enus_09)

    10. Video: Deploying DynamoDB (it_clasaa22_02_enus_10)

    11. Video: Deploying DocumentDB (it_clasaa22_02_enus_11)

    12. Video: Creating Elastic Block Store (EBS) Volumes (it_clasaa22_02_enus_12)

    13. Video: Attaching Volumes to EC2 Instances (it_clasaa22_02_enus_13)

    14. Video: Configuring Elastic File System (EFS) (it_clasaa22_02_enus_14)

    15. Video: Course Summary (it_clasaa22_02_enus_15)

1. Video: Course Overview (it_clasaa22_02_enus_01)

discover the key concepts covered in this course
[Video description begins] Topic title: Course Overview. [Video description ends] [Video description begins] Your host for this session is Dan Lachance. [Video description ends]
Hi, I'm Dan Lachance. AWS provides various storage services, including databases, EC2 instance volumes, as well as the ability to import large datasets from on-premises networks into the AWS cloud. In this course, I'll cover how AWS Transfer and Snow Family services support importing data to the AWS cloud over the Internet, but as well through shipping storage devices physically to AWS data centers.

Then I will plan database usage in accordance with anticipated workloads. Next, I will deploy and manage various database solutions such as MySQL, Microsoft SQL Server, DynamoDB and DocumentDB. Lastly, I'll create and attach an EBS volume and configure an Elastic File System. This course can be used to prepare for exam SAA-C03 AWS Certified Solutions Architect - Associate.

2. Video: Using AWS Transfer (it_clasaa22_02_enus_02)

use a Secure Shell (SSH) client to transfer on-premises files into a Simple Storage Service (S3) bucket
[Video description begins] Topic title: Using AWS Transfer. Your host for this session is Dan Lachance. [Video description ends]
In this demonstration, I'm going to configure the AWS Transfer Family so that I can use SSH with FTP, so SFTP, to transfer files from a Linux host into an S3 bucket. [Video description begins] The AWS Management Console interface is visible on screen. The host is currently on the Console Home page. A Recently visited area is shown centrally, with 14 directories listed within. [Video description ends] So let's first go to the S3 Management Console and check out the bucket that will ultimately be our target. [Video description begins] The Buckets section of the S3 Management Console contains a table with columns: Name, AWS Region, Access, Creation date. [Video description ends]

So I've got an existing bucket here called demo-bucket-3657 and there's nothing in it. So we're going to be using that. The next thing I need to do is I need to set up an IAM role to enable a trust relationship, basically so the permissions are in place for users to do this. [Video description begins] The host clicks on the Search bar found in the top ribbon of the page. He types "iam" into the bar, and selects IAM from the search results. [Video description ends] So I'm going to go to IAM, I'll click Roles on the left, and I'm going to click Create role over on the right for an AWS service.

And I'm going to use EC2 under Common use cases and I'll click Next. Now, what I want to do is I want to attach a permissions policy. I'll search for s3full, and it's going to be the AmazonS3FullAccess policy. [Video description begins] The host selects AmazonS3FullAccess. [Video description ends] So then after that, I'll click Next. For the Role name maybe I'll call it userSFTPAccess and I'll just go down to the bottom right and click Create role.

So it won't take long for that role to have been created, so I'm going to search it up, usersftp, there it is, UserSFTPAccess. What I need to do here is go to Trust relationships, Edit trust policy. Now, currently the allowment of, of access to services is for "ec2.amazonaws.com". [Video description begins] The host erases "ec2" from the line of code. [Video description ends]

To use AWS Transfer, that needs to say "transfer.amazonaws.com". OK. Once it does, you can click Update policy and that part is done. So if I search for sftp here up at the top and go into AWS Transfer Family, we can set up our SSH-based SFTP server. So in the Servers view on the left, we don't have any Servers shown on the right because it's not ever been set up, so I'm going to go ahead and click Create server.

And we have a choice of the protocol support we want to enable for our file-based server. I'm going to leave it on the default of SFTP (SSH File Transfer Protocol), and I'll click Next. I'll leave it on Service managed where I get to control the user accounts with this specific service as opposed to linking my SFTP server to AWS Directory Service or something like that.

So I'm just going to go ahead and click Next. I'm going to leave it as being Publicly accessible over the Internet in this particular case, and I'll just leave it on None to use the default server endpoint. If your organization or agency needs to comply with Federal Information Processing Standards or FIPS, then you could enable it as a FIPS Enabled endpoint.

I'm not going to do that, I'm going to click Next. Now, I want to allow access to an S3 bucket, so I'll leave it on Amazon S3 and I'll click Next. So I'm just going to scroll all the way down, I'm not going to change anything here and I'll click Next. And then in the bottom right I'll click the Create server button. OK. Our server is shown as being listed here with No users. [Video description begins] On the Servers tab there is a table with columns: Hostname, Server ID, State, Service managed users, Endpoint type, Domain. The Server ID reads: s-24d4e27f2d28486c9. [Video description ends]

So if I select the checkmark to the left of the server, then the Add user button becomes available. Let's add user mbishop, and for the Role I'm going to assign this user it's going to be the custom role we created that allows S3 access to the bucket. And I'll choose the demo bucket that we specified earlier when we were taking a peek around.

Now, for the SSH public key, I need a public and a private key pair if I don't already have one generated. The public key gets pasted in here and gets stored server-side, the private key is on the station you will use to transfer files into the S3 bucket over SSH with FTP, or SFTP. One way to generate a key pair if you haven't got a pair already [Video description begins] The Command Prompt interface is shown on-screen. [Video description ends] is to use the ssh-keygen command, whether you've got Linux support on Windows or whether you're at a Linux host.

So it's going to generate a unique public and private rsa key pair. It wants the default file name to save the private key in, the file will be called id_rsa, I'm OK with that. [Video description begins] The host presses Enter on the keyboard. [Video description ends] I'm going to put in a passphrase. Private key files should always have a passphrase for security reasons and I'll enter the same passphrase again. [Video description begins] The host presses Enter two times, not writing anything for a passphrase. [Video description ends]

And notice what it will have done is in the same directory it will've created the public key in a file called id_rsa.pub. So if I navigate to that directory location and type dir, there are the two files. I'm going to use notepad though to open up the id_rsa.pub file.

And what I need to do here is I need to copy this public key in its entirety, because that is what I'm going to paste into the SSH public keys field here to create user mbishop, so let's go ahead and click Add. And then it says it successfully created our user mbishop. So now if I go and click on the Server ID link under Users, mbishop is shown here.

And notice the Home directory is in the bucket in a folder called mbishop, and under Public keys it has a value of 1. What I need to do here is copy this Endpoint. This is the default DNS name for this SFTP server and I need that if I want to make a connection to it. And so from the command line on my machine, I'm going to run sftp -i, and I'm going to specify the name of my private key file which is id_rsa.

Then I'll specify username mbishop@ and I'll paste in the DNS name of our AWS Transfer server and I'll press Enter. Now, the first time you connect, you'll be asked to trust that host. I've already specified that, yes, I want to trust it. So what it's asking for is a passphrase for my private key file. OK, so I'm going to go ahead and enter that in.

All right. I am now authenticated to my SFTP server. If I type pwd for print working directory, it tells me I'm in my demo-bucket-3657, in a folder called mbishop. If I type ls, nothing is in there. So I'm going to use the SFTP put command to put a file that I know I have in my local SSH folder on my local machine, called Project_A.txt, I'll press Enter.

OK, it's uploading it. If I do an ls, now that file shows up in my S3 bucket folder. Let's check our work in the console. So back here in the console, I'll search for s3, we'll go into S3. We need to go into that demo bucket. What do you know? We've got a folder called mbishop. Within that we've got our Project_A.txt file. So it worked. We were able to use SFTP over an SSH encrypted connection, to get content into an S3 bucket by configuring an AWS Transfer server.

3. Video: AWS Snow Family (it_clasaa22_02_enus_03)

recall when to use AWS Snow Family options for large data transfers
[Video description begins] Topic title: AWS Snow Family. Your host for this session is Dan Lachance. [Video description ends]
One interesting aspect of storage in the AWS Cloud is how you get vast amounts of data that you might already have in a data center on-premises into the cloud. Assuming that that allows you to remain compliant with relevant laws and regulations.

So we're talking about importing large amounts of data into AWS or even doing the opposite. You might have vast datasets in AWS that you now want to have on-premises, so you can run export jobs. Now, when we say large amounts of data, we're talking about many, many terabytes, even petabytes worth of data.

So a lot of data. That brings us to the AWS Snow Family of services. What is this about? Well, what these are all about are services that deal with physical storage devices that you can copy data to once they're shipped to your location. They're secured with encryption and then you send them back to an AWS data center where technicians then copy them into an S3 bucket.

Of course, that's an import job into the cloud. You can also do the opposite to export data from AWS. So AWS Snow Family consists of AWS Snowcone, AWS Snowball and AWS Snowmobile. Well, let's talk about these in a bit more detail, starting with AWS Snowcone.

AWS Snowcone is a rack-mountable device used for storage, and it comes in a couple of variations like solid state drives in the amount of 14 terabytes or hard disk drives in the amount of 8 terabytes. Now, when you get this device shipped to your location, you plug it into your network, you plug it into a power source and you power it on.

Then you unlock it. You can use the AWS Management Console to look at your Snowcone job to get the 29-character unlock code that decrypts the manifest on the device so you can start using it, and then you can copy data to it using an NFS mount point. So you can use this for offline data transfer because it's a physical device you can copy data to.

It gets encrypted, you ship it back to a data center. You can also use AWS DataSync, which is pre-installed on it essentially so you have a storage device on the edge of your network allowing quick access on your on-premises network environment, but in the end, it's being stored in the cloud.

But when you talk about vast amounts of data, that's probably not sufficient if you want to get a lot of data into the cloud, because it would take too long, even over the fastest of Internet connections. So there's 256-bit encryption for protection of data at rest on Snowcone devices.

They also use Trusted Platform Module or TPM as an anti-tampering mechanism on the device. And after your data, in the case of an import job, is copied from the Snowcone device into an S3 bucket by an AWS technician, then NIST guidelines are followed for the secure removal of the data from that device.

So there are no artifacts left over that might in the future be recovered by somebody else. AWS Snowball is next in line. It has Edge Compute Optimized options. What this means is, aside from doing what Snowcone can do, you have a physical device that you can copy storage, that you can copy files to, before you ship them off to an AWS datacenter.

Edge Compute Optimized means it's on your on-premises network edge with the ability to run some kind of compute analysis on data. Now, why would you want to do that? You might want to analyze some data, maybe analyze video, you might want to analyze ingested data that's copied to the Snowball device before it actually gets stored into the cloud, to see if it's a worthy candidate.

You can also use this as a useful way to have some kind of compute functionality on your data, even if you don't have a connection to the internet into the AWS Cloud at that time. And so it uses AWS Lambda functions to do this type of processing. Now, to work with this, you would download the freely available Snowball Edge client to unlock the device once you power it up and then copy your data to it using either the S3 GUI or an NFS mount point.

Of course, using AWS Snowmobile, which was the third service in the Snow Family, literally involves large transport trucks with trailers full of storage appliances, and that would be for the largest amounts of data that you want to perhaps get into the AWS Cloud, perhaps for a government agency.

So working with the Snow Family means that in the console you would create a Snow Family job. In our screenshot, note that we have the option when we configure the job to determine if we are importing data into Amazon S3 or exporting data from Amazon S3. If we just want local compute and storage only, perhaps in a disconnected environment, we even have an option to import virtual tapes into the AWS Storage Gateway.

Now, once you go through and configure the job, you will also be specifying shipping information so the device can be shipped to your location in the case of importing data into Amazon S3. And the creation of that job will actually trigger the device to be shipped to your location after you complete it, so you can track the status of a job using the console or even programmatically using the appropriate API. Yet another interesting option here, if you're going to be working with a number of Snow devices, is to use OpsHub. [Video description begins] A screenshot of the AWS Snowball Console interface is visible on-screen. It contains a menu with tabs: Overview, Features, Pricing, Getting started, Resources, FAQs, Customers. The Resources tab is currently selected and AWS OpsHub is visible. [Video description ends]

So this is a GUI, a free download, that you can install and run on your Windows, Mac, or Linux host, which will let you manage your Snow Family devices on your network, including unlocking them, configuring them, providing drag and drop services for data, being copied to devices, and monitoring device metrics, so you can track the disk I/O performance on these devices. So you can consider the Snow Family suite of options as most often being used for migration of large amounts of data into the AWS Cloud. That's not all it's for, but it is common.

4. Video: Creating an AWS Snow Family Job (it_clasaa22_02_enus_04)

configure data transfer into a Simple Storage Service (S3) bucket
[Video description begins] Topic title: Creating an AWS Snow Family Job. Your host for this session is Dan Lachance. [Video description ends]
In this demo, the focus is going to be on creating an AWS Snow Family job. Now, is the point to memorize every single step and every attribute that you need to specify? The answer is no, not at all. The key here is we have to know what it is and when to use it.

So AWS Snow Family is a collection of services that essentially lets you migrate large amounts of data into the cloud or export them from the cloud. Now, this is done because AWS Snow Family uses physical storage devices that would be shipped to your location, you plug them into your network, you give them power, you power them up, you get an unlock code from the console to unlock the device and you can start copying files to it.

Then you ship it back to an AWS datacenter. That is the general high-level overview, but let's dig a little bit deeper. Here in the console, I'm going to search for snow, and from the search results, I'll click AWS Snow Family. I have some Pricing information for AWS Snowcone, Snowball and Snowmobile. I'm just going to click on Order an AWS Snow Family device.

Now, at this point we are asked, do you want to import data into Amazon S3? That means AWS will ship us an empty device or multiple empty devices for us to copy our files to. Now remember, you would do this when it would just take way too long to do it over even the fastest of network connections.

Take, for example, the many websites that are freely available where you can calculate how long it would take to transfer files, in this case, let's say 72 TeraBytes, over a 300 megabyte per second link. Now that's upload, that's not download. So depending on the type of network connection you have, whether it's synchronous or asynchronous, will determine what the upload speed is.

You'd have to know that. And then accounting for a little bit of overhead on that link, we can click the Calculate button, and in this case it says a file that's 72 TB in size would take at least 3 days, 4 hours, 53 minutes, 44 seconds to transfer over that type of speed. Now, take note that in my selection it was megabytes per second, capital M, capital B, not megabits.

So if we were to choose 300 megabits per second and then Calculate that, wow, it would take 25 days, 15 hours, 9 minutes, 52 seconds. You get the idea. When you have large amounts of data, it might just be quicker to copy them to a secured storage device and ship it off to a datacenter.

So that's why we're doing what we're doing so we can import into Amazon S3, we can export from Amazon S3, we might want a Snow device in our on-premises network environment for local compute and storage, or we can import virtual tapes into the AWS Storage Gateway. We'll be looking into the AWS Storage Gateway separately.

In this case it's going to be Import into Amazon S3 and I'll click Next. It then talks about how you can try to benchmark how long it might take and how much space you're going to need in the end, to accommodate your data. So I'm just going to tick off the checkbox here that says I acknowledge I have read the information above and I'll click Next.

So we can use an existing address if we've done this before or we can add a new one, I'm going to fill in some fictitious information because I'm not really going to order the device. Then I'll scroll all the way down, the Shipping speed I'll leave it on One-Day Shipping and I'll click Next. OK. And the next thing we have to do is specify the name of our job. I will simply call it Job1. Not very creative, but that's OK for this example. And then we get to select the device. Is it Snowcone, Snowcone Solid State Drive or SSD, or Snowball Edge Storage Optimized?

Well, I definitely want Solid State Drive, so I'm going to select that and I can determine if I will provide my own power supply and ethernet cable. I can then choose the S3 storage location I ultimately want data to appear into, so I can select that. [Video description begins] The host selects samappv2 from the table containing S3 bucket names and their date of creation. [Video description ends] It says here that the buckets that you select here will appear as directories on your device when you receive it.

OK, so I'll just use a couple of those S3 buckets. I'm not going to use EC2 instance compute services or IoT Greengrass, but I am going to turn on Remote device management using OpsHub or the Snowball Client, and I'll click Next. Now, it does encrypt the contents on the storage device, which is good, so we can specify a key. Now, we might have created a key management services or KMS key, so I'll just go ahead and select one of the keys that we've created and I'll click Next. [Video description begins] The host selects samplekms under KMS key. [Video description ends]

Now, as my job changes status, I want to know about it. So I'm going to use an existing SNS topic that I already have here to receive those notifications. Otherwise I could create a new one; SNS is Simple Notification Service. And then we have our job. All of this information that we specified in each section is editable. We've got an Edit button if we need to make a change.

And at this point, if we want to continue with the process, we would actually click the Create job button. So I'm going to go ahead and click Create job. You've got one hour to cancel the job without incurring charges, so be sure, if you're experimenting with this, to delete it. [Video description begins] The AWS Snow Family console is on-screen. The left-hand vertical menu has tabs: Home, Large data migration plans, Create job, Jobs, Prepaid jobs. The Jobs tab is currently selected. On the right, we se a table with columns: Job name, Device, Created date, Job, Status. [Video description ends] So here we have Job1, it's a Snowcone SSD type of Device, it's an Import Job.

If I click on the job itself, it says that the job has been created and it's been queued. Notice on the left that the status will change to Preparing device, Preparing shipment and all of these other items. [Video description begins] The host goes back to the Jobs page seen previously. [Video description ends] So I'm going to select the job here and from Actions I'm going to choose Cancel job and onto the job named Job1 and I'll choose Cancel job.

5. Video: AWS Database Capacity Planning (it_clasaa22_02_enus_05)

recognize when to use various AWS database services including Relational Database Service (RDS) Proxy
[Video description begins] Topic title: AWS Database Capacity Planning. Your host for this session is Dan Lachance. [Video description ends]
It's important to carefully plan out how databases will be used in the Amazon Web Services Cloud. And so it's important to focus on database capacity planning. You might have web applications or a line of business that's perhaps even only used internally. Maybe they run on mobile devices and send data to a central database. Whatever the case might be, you need to know how databases will be used to perform database capacity planning.

This means thinking about the amount of data that's going to have to be stored. And that brings into question, for how long? If we store data in a database for long periods of time, we're going to need more space to accommodate that, whereas if we have backups that get archived and rotated periodically, that might lessen the amount of database storage space that we will use.

We have to think about the frequency of data. Are we ingesting a live stream of data over the Internet? And so we have to make sure that we have quick or elastic rapid provisioning of database storage. We also have to think about the type of data that will be stored. Is it going to be structured data? For example, do we have a customer sign-in portal on our web application that will always store customer information like email addresses, phone numbers, payment methods and so on?

Or do we have unstructured, unpredictable data on a large scale, of many different types, so less structured? That's going to determine what type of database you use. More on that in a minute or two. Then we have to think about storage and database connection capacity. How many concurrent connections might we have during peak usage? That might be certain times of the day.

The pattern might be certain times of the week, certain times of the month, only when there's sales, if you're in retail or only seasonal. You have to monitor your application and backend database usage over normal usage to determine what the standard baseline is. That will vastly improve the overall performance if you apply that learned knowledge to your database capacity planning.

Even if you have metrics for that type of performance on-premises, perhaps because you've run a solution on-prem for the last couple of years and now you're going to migrate it into AWS. That's still going to be enormously helpful to help you rightsize your solution in the AWS Cloud. And of course we have to plan for failure.

It's inevitable over time. Things will fail, they will slow down, and so we want to have a proactive approach to that. Resiliency to failure means a couple of different things. It could mean, do we have server failover in an active/active environment? We have a couple of servers always up and running, if one fails, the other one kicks in immediately.

Well, we'll talk about the RDS proxy in a couple of minutes, which kind of deals with that. Resiliency to failure also means other things, like do you have an incident response plan to minimize the RTO, the recovery time objective to get things up and running as quickly as possible? Do you have multiple database replicas? Perhaps some are read only, some are read/write.

How often are you backing up your data? And where is that data backup stored? The last thing you want is everything available online all the time because a ransomware infection could also affect your backups. All of these things we're talking about end up being fine-tuned granular details depending on the type of database you're using and how you're using it.

Now, part of planning is the type of database you will use. There are two general categories, NoSQL databases. NoSQL means not SQL. An example of that would be DocumentDB or DynamoDB in the Amazon Web Services Cloud. A NoSQL database either does not have a structured schema or it has a loosely structured schema.

The schema in a database is a blueprint for what will be stored in it. Now, think about a standard SQL-compliant database. SQL meaning Structured Query Language. In AWS, there are many SQL-compliant solutions available through relational database service or RDS. This is a managed service where you can run databases and Amazon takes care of the underlying virtual machines that run it.

There are some variations on that where you can have a bit more control of the underlying instance, but generally, it's a managed service. But SQL uses a structured schema. The blueprint or definition of what will be stored in the database is very rigid and specific, such as in the customer's table we will store the customer ID, the date they became a customer, the first and last name, email address, phone number, payment preferences, that type of thing.

And you can only store that type of information within a table with that type of definition. So it then becomes very apparent when you should use a NoSQL database versus a SQL database, or maybe a hybrid of both for certain parts of an application. Pictured on the screen, we have a screenshot of RDS database engine options.

So when you go to deploy relational database service in AWS, you will have the option between a number of different database engines like Amazon Aurora, MySQL, MariaDB, PostgreSQL, Oracle and Microsoft SQL Server. Now, depending on your selection, will determine what you select down below for the version of that engine.

You might need a specific version of that database engine to support some aspect of your application. Now, if you're the AWS Cloud technician and not the database or web app developer, you need to talk to them to find out what the appropriate selection is here.

And there are more options to select beyond just this, such as the listening port, whether the database should be publicly accessible over the Internet, for remote management from on-premises. And you might determine that, well, I already have some licenses for Microsoft SQL Server that we will no longer be using on-premises, so there is a bring-your-own-license, a BYOL.

You'll have some other options down below where you can specify things like your database encryption, database backups, and so on. One of the things that is very helpful with database capacity planning is simply monitoring data usage patterns over time. Now, you can set that up and even receive notifications when certain metrics exceed a certain value. You can do all of that using Amazon CloudWatch.

You might also consider sizing databases so that they have some extra storage, memory, and compute power always available to accommodate unpredictable demand spikes. Now, if you're using a database solution that supports automatic scaling based on usage, then that might already be taken care of. You should consider the average concurrent number of connected users over time during normal usage.

Again, setting a baseline of normal performance because that's going to help you so, so much. Otherwise, you're guessing it. You are working in the dark when it comes to trying to rightsize your database solution. When we talk about the amount of data that the database will handle, we're talking not only about what will be stored, but also the amount of data into and out of the network on a daily basis.

That also has cost impacts that we need to be aware of, depending on the amount of data that we're talking about. We might consider using provisioned IOPS storage versus the older, slower magnetic storage to address busy disk I/O usage. IOPS stands for input and output operations per second. More IOPS means quicker throughput in the underlying disk subsystem.

Now, depending on your database environment, it might be heavy on writing. And so you need to use a high-provisioned IOPS value. Or maybe your database is more on the querying side where you have in-memory caching, where there is less disk I/O. So think about usage patterns for how you will be using the database.

And then you can get very specific with the actual structure of the queries themselves. Are the queries created in an efficient manner so that we focus on querying, sorting and grouping on index values? If not, you might want to go back and configure new indexes for things you search for frequently. In a perfect world, you would have enough memory or RAM allocated to your database solution so that your most common working set of database data is resident in memory. Not all of it all the time, but the most common working set.

If it can be retrieved from memory that's going to be much, much quicker, thousands of times quicker actually, than retrieving it from even the fastest provisioned IOPS disk subsystem. Now, one tip I've learned to rely on when it comes to that is using the CloudWatch metric named read IOPS.

So what are the disk I/O operations per second for reading? That should be a low value if most of your working set is in memory most of the time during normal database load. And again, the key is under normal database load over time. Well, how long? What's common is if you get one week of normal usage of a database solution.

Pictured on the screen, we have a screenshot of RDS database compute and storage configuration. It's kind of like setting the instance type for an EC2 instance, so you get to determine the underlying horsepower, the amount of virtual CPUs and the amount of RAM and the network throughput supported. All very important to pay attention to and you can change it after you deploy your RDS solution.

That's what right sizing is about. Make sure you have the correct horsepower to accommodate your workload with a bit of extra buffer space. [Video description begins] In the screenshot, we have a section titled DB instance class and another one called Storage. DB instance class has two selectable options: Standard classes (includes m classes), Memory optimized classes (includes r classes). Standard classes (includes m classes) is currently selected. The Storage section has dropdown menus for Storage type, Allocated storage, Provisioned IOPS. [Video description ends] Then down below in our screenshot we have Storage options. What's been selected here is Provisioned IOPS, where you could specify the amount of Allocated storage in gigabytes and Provisioned IOPS. Finally, another thing to consider is when to use the RDS proxy.

Now, the RDS proxy, like RDS in general, is a managed service. You don't have to set up virtual machine instances or anything like that. That's handled for you. But what is this? What proxy does here for RDS is it pools database connections together in memory to increase connection scalability.

Now, what we're really doing here is we have a centralized way to manage database connections while removing it from the backend databases themselves, thereby freeing them up to do what they do best. Database stuff. Speaking of centralized, RDS proxy also lets you configure centralized credential management because it integrates with AWS Secrets Manager. And finally, RDS proxy can reduce failover time because it supports something called automatic database failover, which means you don't have to wait for DNS changes to be in effect before you can connect to a new failed-over database host.

6. Video: Deploying MySQL Using the Console (it_clasaa22_02_enus_06)

deploy and configure MySQL in AWS
[Video description begins] Topic title: Deploying MySQL Using the Console. Your host for this session is Dan Lachance. [Video description ends]
MySQL is an open-source relational database solution. It's been around for quite a while. But the great thing about working with RDS, with relational database services in the Amazon Web Services Cloud is that all of the underlying work is done for you. That means there's no need to manually provision virtual machines that you then would install the MySQL database server software on. That part is all done for you.

Instead, you focus on what databases are supposed to do; store data efficiently and allow the querying of that data. So to get started here in the AWS Management Console, I'm going to search for rds and then I'll click on that to open up the RDS Management Console. And on the Dashboard landing page I'm going to go ahead and click Create database.

You can choose Standard create where you get to specify some config details such as those that are related to security, backup schedules, maintenance windows, or you can just choose Easy create and use best practice configs and then you can change them after it's created if you so choose. I'm going to leave it on Standard create. Down below, the engine we're interested in, of course, is MySQL.

Now, why would you choose MySQL over Microsoft SQL Server? Well, Microsoft SQL Server is proprietary and you have to purchase licenses. You don't have to do that for MySQL, and you might be familiar with MySQL, or you might have an app that needs to use a MySQL database in the backend. So there are many reasons that you would choose one relational database solution over another.

So MySQL it is. Now, of course, down below it states that we're using MySQL Community edition. OK, that's great, don't have to pay, at least for the MySQL component itself. You're going to have to pay for having it running in the Amazon Web Services Cloud, though. You get to choose the Version of the MySQL Engine.

This could be important depending on the feature set that you want to take advantage of. So I'll leave it on the latest Version, MySQL 8.0.28. Then a template. Do we want to use a Production set of options for fast consistent performance, or Dev/Testing, or just Free tier usage.

If you wanted to know what the Free tier selection would include, you can just click Info and you'll see the number of hours that you can run in a single Availability Zone, the amount of storage and the type, backup details. So I'm going to go ahead and choose Free tier in this particular case. So down below, a lot of the options are grayed out because of that selection, like the Multi-Availability Zone Cluster settings.

Now, for high availability, depending on how this database will be used, that might be very important so you might want to use Dev/Test or Production. If I go to Dev/Test, those become available, same thing is true with Production as a template, but back to Free tier, down below it wants a database instance identifier.

I'll leave the default value of database-1. It wants Credential Settings. The default username is admin, I'll specify and confirm the Master password, and then I have the DB instance selection. Many of them are grayed out again, because I'm using the free tier, but this is important because you have to right-size it.

You have to make sure you have the appropriate amount of virtual CPUs and RAM, and potential network throughput available for the workload that will be supported by this. You can always change this after the fact. [Video description begins] In the dropdown menu under Burstable classes (includes t classes), the host chooses db.t3.micro. [Video description ends] Here's the Storage 20 GiB, and I'll leave Storage autoscaling enabled so that if we need more space then the space will be allocated as needed, up to a maximum of, in this case, 1000 GiB.

Connectivity over the network will be IPv4, but you could choose a dual-stack for IPv4 and IPv6. I'll leave it. Set to use my Default VPC. Down below I'm going to choose Yes for Public access because I want to be able to use tools from an on-premises computer to reach into AWS to manage MySQL, for example, we'll be using MySQL Workbench, but that connectivity will show up in another demo.

I'm going to choose to Create a new VPC security group, I'll call it MySQLSecurityGroup, and in Additional configuration the listening port for MySQL is normally 3306. I'm OK with that, I'll leave it. Database authentication is just standard Password authentication. Under Additional configuration, this is where we could specify things like whether automated backups are enabled and for how many days backups are retained, and whether we want to Enable encryption.

Notice that these things are all turned on by default. We can also turn on Deletion protection as an additional layer of security against accidental deletion of this database. And then finally, in the bottom right I'm going to go ahead and choose Create database. All right, and before too long we'll have a message at the top [Video description begins] On the Databases screen, there is a table with columns: DB identifier, Role, Engine, Region & AZ, Size, Status, CPU, Current activity, Maintenance, VPC. [Video description ends] that states that it successfully created our database.

It's called database-1. And if I scroll over, it's a MySQL Community edition configuration and the Status is Available. Now, if I click on the link for the database identifier that opens up its properties. I can get a listing of things like the number of concurrent connections, CPU activity, the database Class, the Region it was deployed into, and I can click the Modify button if I need to make some changes to the config of this.

So we're presented with our options like maybe setting a New master password or changing the size, changing Storage settings, autoscaling, all of the same stuff that we saw upon creation. I'm just going to click to close that and go back to Databases. Let's go back in and just view the details of the database. Down below, under Connectivity & security, [Video description begins] Underneath the Summary section, there is a menu with tabs: Connectivity & security, Monitoring, Logs & events, Configuration, Maintenance & backups, Tags. [Video description ends] we've got our DNS Endpoint for connection purposes over Port 3306.

Notice that Public accessibility is set to Yes so that if I wanted to, I could manage this instance over the Internet from on-premises. Depending on your security requirements, that might be unacceptable. You might only leave it private so that you have to, for example, VPN into the AWS Cloud first before you can get connectivity.

And down below, I can click on the Monitoring tab to monitor some performance metrics related to this database instance, I can go to Logs & events to view log activity, go to Configuration, which gives us a summary of what we had configured and we know that we can modify these settings. Maintenance & backups, which we know is on by default, but we can configure it otherwise.

And finally, we can add up to 50 key and value tag pairs as metadata for this database. If I go back to the Databases view and select the database with the radio button on the left, under Actions I can choose to Stop the database, Reboot it, Delete it, which is important if you're only testing and then you're finished with the testing,

Stop it, and ideally, if you know you won't need it, Delete it, otherwise you're still incurring charges. Even if it's stopped, you're incurring storage charges. You can create a read replica for high availability, you can take a snapshot, and you can restore it to an earlier point in time because backups are enabled by default.

7. Video: Managing MySQL in AWS (it_clasaa22_02_enus_07)

connect to MySQL in AWS using MySQL Workbench
[Video description begins] Topic title: Managing MySQL in AWS. Your host for this session is Dan Lachance. [Video description ends]
In this demo, the focus is going to be on how to make a connection from an on-premises management station into the AWS Cloud so that you can manage a deployed MySQL database. [Video description begins] An internet browser is shown on-screen, with two tabs: one displaying AWS Management Console, the other a MySQL website with the url "mysql.com/products/workbench". The tab displaying MySQL website is currently selected. [Video description ends] So the first thing we'll do is examine the configuration of our RDS database environment for MySQL and then we'll make the connection using MySQL Workbench. MySQL Workbench is a free, open-source tool that you can choose to download.

I've actually already got it installed and running on my on-premises computer. Think of it as a GUI database management tool for MySQL. So if I switch over to the AWS Management Console, I can then go into RDS, Relational Database Service, and check out what I've got running. If I click the Databases view on the left and I'm in the North Virginia, us-east-1 region, always pay attention to the region.

I do have a database here, it's called database-1. It's a MySQL Community edition database. I also have a reference here for the database sizing, the underlying horsepower, the Status is Available, not very much CPU utilization, 0 Connections. OK. So there's not really much going on with that particular database. Well, when you deploy databases in the cloud using RDS, it's a managed service.

Platform as a Service really. You don't have to manually provision the underlying virtual machines, you don't have to install database engine software. It's done for you. But you need a way to connect to it to manage it so you can actually start working with data. So I'm going to click on the database identifier to open up the properties of it.

I'm interested, under Connectivity & security, in taking note of, well, specifically copying the DNS database Endpoint there. So I'm going to go ahead and copy that to my Windows clipboard. Notice the default listening Port is standard for MySQL, it's 3306, that's TCP. So if I fire up the MySQL Workbench tool on my on-premises computer, this is what I get. [Video description begins] The MySQL Workbench interface is shown on-screen. It contains a horizontal menu with the tabs: File, Edit, View, Database, Tools, Scripting, Help. In the main area, there are buttons: Browse Documentation, Read the Blog, Discuss on the Forums. Underneath, there is a MySQL Connections section, with the buttons to add or configure a connection. [Video description ends]

So I can then click the add button next to MySQL Connections. I can name the connection, maybe I'll call it MySQL in AWS. For the Hostname I'm going to paste in that connection endpoint that I copied from the console, Port is 3306, standard for MySQL, [Video description begins] The Hostname reads: database-1.c373bksoyaf5.us-east-1.rds. [Video description ends] Username is not root, in this case it's admin. I can actually store the Password in a vault here, it's managed by the MySQL Workbench tool, and that's it.

Well, that's it at least for specifying those items. Next thing we can do is click the Test Connection button and hopefully it'll come back and say it Successfully made the MySQL connection. If it didn't, it could be a firewall issue. TCP port 3306 might not be allowed, it might be blocked, or you might not have public connectivity available on your database instance.

You can check that back here in the console when you're under Connectivity & security for your database. Over on the right, down under Public accessibility, it's set to Yes. I set that when I deployed this to allow connections over the Internet which is what we're doing now. If that's not set, you can click Modify and make many different changes to the configuration of your database instance.

Back in MySQL Workbench on-premises, I'm going to click OK. So I've now got my stored connection which I've named MySQL in AWS. Pretty slick. If I click on it, it's going to make the connection into the AWS Cloud to my database instance. And that's it. We are in. If I click Server Status on the left I get some details about the Server Status, like the specific Version that we are running. If I click Users and Privileges on the left, this is standard MySQL config stuff where we could add MySQL-specific accounts. There's the admin account that we actually signed in with. I can go to Data Import and Restore, to bring data into MySQL.

Now, this is all Administration. If I click Schemas, I can view some database schema details so I can go down into Tables where I could even right click on table and choose Create Table, and from there start defining my table definition and its columns. Same thing goes for Views, Stored Procedures and custom Functions. Of course, you can also use the toolbar buttons at the top, such as to Create a new table or to Create a new view, or to Create a stored procedure, whatever the case is within the database that it is that you need.

Back here in my Databases view, if I click refresh, notice that we have some Connections now. Even though I'm only one user, it will make a couple of extra connections in the background when I'm using specific tools like my SQL Workbench. So we've now been successfully able to connect into our MySQL RDS-deployed instance from an on-premises management station.

8. Video: Deploying Microsoft SQL Server in AWS (it_clasaa22_02_enus_08)

deploy and configure Microsoft SQL Server in AWS
[Video description begins] Topic title: Deploying Microsoft SQL Server in AWS. Your host for this session is Dan Lachance. [Video description ends]
All right. In this demo, I will be deploying Microsoft SQL Server in AWS. Now, I'm not going to be deploying a standard EC2 instance and manually installing the database software. Instead, I'll be using RDS, Relational Database Service, where I have the option of leaving all of that underlying infrastructure grunt work to Amazon Web Services.

So here in the Console, I'm going to search for rds. I'll click RDS in the results. [Video description begins] The RDS Management Console interface is shown on-screen. On the left-hand side, there is a vertical menu with the tabs: Dashboard, Databases, Query Editor, Performance insights, Snapshots, Automated backups, Reserved instances, Proxies. [Video description ends] And if I go to the Databases view, any existing database instances, and there might even be something different than Microsoft SQL Server, will be shown in this list. Instead, we have a message that says No instances found. So I'm going to go ahead and click Create database.

And it's at this point that you get to choose which engine you want to use, whether it's Amazon Aurora, MySQL, MariaDB, or in our case, Microsoft SQL Server. [Video description begins] The other Engine types are: PostgreSQL, and Oracle. [Video description ends] But notice up above, it's set to the Standard create where you can configure some settings related to the database.

Those related to high availability, security, backups, maintenance windows, or you could just choose Easy create where all those defaults are set, and if you need to change them, well, you can go in and change them after the fact. I'm going to leave it on Standard create. So we've already selected Microsoft SQL Server below.

The next thing to do is choose the management type. If we choose Amazon RDS, this is the standard managed service, which means automated patching of the underlying virtual machine OS and the database software. But if you need more flexibility, more control, you can choose Amazon RDS Custom, which gives you access to the underlying OS.

I don't need that, I'm going to leave it on Amazon RDS. Then we have to choose the appropriate Microsoft SQL Server Edition. So depending on what you need to do will determine what you select. So if you need a lot of high availability, advanced functionality, you're going to need to be using SQL Server Enterprise Edition. But I'm just going to go ahead and stick with the standard SQL Server Express Edition, which maxes out at a database size up to 10 GB.

Then we have to select the specific Version of the SQL Server Engine. I'll leave it on the newest version shown in the list. [Video description begins] The host selects SQL Server 2019 15.00.4198.2.v1 from the dropdown menu under Version. [Video description ends] Down under Settings, it's got the database identifier set to database-1. I can change that now or after. I'm going to leave that for now. The default username is admin and we can auto generate a password or specify one. Well, I'm going to specify and confirm my own custom password.

Down below, under Instance configuration, we can select a DB instance class which allows us to determine how many vCPUs, how much RAM is available. I'll leave it on db.t3.small. If I scroll down I can specify Storage details like the Storage type, the Allocated storage, and whether I want autoscaling for storage for allowing automated growth as needed, up to the maximum threshold, well, here it's got 1000 GB, but we know that SQL Server Express Edition maxes out at 10 GB.

Scrolling down, I only want IPv4 connectivity, I'll let it use my Default VPC, and I want to enable public accessibility. By default, it's set to No, I'm going to choose Yes, and I can change this after the fact if I want to. I'm going to create a new security group called MSSQLServerSecurityGroup.

I can use this for multiple SQL Server instances if I deploy them. So down under Additional configuration the standard SQL listening port is 1433. I'm going to stick with that. I'm not going to Enable SQL Server Windows authentication. I'm just going to use standard SQL logins. Down under Additional configuration, we have database parameter groups, Option groups, Time zone preferences.

These are all specific granular details. What I'm looking for here is the fact that automated backups is enabled with a default retention period of 7 days, and I could Enable deletion protection to protect from accidental deletion of my SQL Server instance. And I have a bit of a sense here of what it's going to cost on a monthly basis. [Video description begins] The Total cost reads: 34.42 USD. [Video description ends]

You want to be very careful with RDS database services that you deploy. Make sure that they're needed and are being used for business purposes. Otherwise, if they're just deployed and running, it's going to incur large monthly costs that you don't need. So in this case, I'm going to go ahead and choose Create database, and as it says at the top, it might take a few minutes for this to get created.

OK. So while the database is still launching, if I click on the database identifier it takes me into the properties where I can see the CPU utilization, the number of active sessions, the database Class or the instance type, the Region and Availability Zone where it was deployed, and down under Connectivity & security I have important connectivity information like the DNS Endpoint name and the Port that it's listening on, which of course is 1433.

I can also go to Monitoring to view some other performance metrics related to this database instance. This is going to be important when it comes to monitoring the database during normal usage to see if you need to scale up. We can go to Configuration to get some details about how it's configured, such as the fact that Encryption is Not enabled, and we can also go to Maintenance & backups to see that configuration.

But notice we've also got an Automated backups view over here on the left. And remember that backups are enabled by default. Now, when I go back to my Databases, if I open that database up again by clicking on its ID, I can choose to Modify the database. I can reconfigure it if I decide, for example, that I need more or less horsepower, I want to change the database sizing, I can go ahead and do that.

So I will go down, in this case, under Instance configuration and make the appropriate selection and whatnot. Also, if I select the database radio button, I can also go to the Actions menu, I can Stop the database, maybe I want to keep it, but I don't want it running right now. I want to Reboot it, because something doesn't seem to be working correctly with the underlying instance.

I want to Delete it perhaps, Take a snapshot or Restore it to an earlier point in time, because of course backups are automatically being taken. Now, compared to setting up an entire server operating system and then installing all the tools required for Microsoft SQL Server, that is a pretty quick deployment.

9. Video: Managing Microsoft SQL Server (it_clasaa22_02_enus_09)

connect to Microsoft SQL Server from on-premises
[Video description begins] Topic title: Managing Microsoft SQL Server. Your host for this session is Dan Lachance. [Video description ends]
You can download Microsoft SQL Server Management Studio, otherwise called SSMS, for free. This is a graphical interface tool that lets you make a connection to a SQL server, whether it's on-premises or in the cloud, so that you can manage databases in the entire environment. I've already downloaded and installed SSMS on my on-premises computer.

So let's go into the console and take a look at what we've got for databases. I'm going to go to the RDS console and on the left I'm going to go to Databases. OK. So I've got a database, the identifier is database-1, it's a Microsoft SQL Server Express Edition configuration, the region and Availability Zone are shown, the database Size is shown, the Status is Available, there's not a whole lot of CPU activity, around 7%, and there are no current sessions.

Now, what I can do is click on the database identifier link to open up the properties of the database. Now, I could modify the configuration under the Actions menu, I could Stop the database, Reboot, Delete it, Take a snapshot, Restore it from backup. But what I want to do here is, down under Connectivity & security, I want to copy the Endpoint. [Video description begins] The Endpoint reads: database-1.c373bksoyaf5.us-east-1.rds.amazonaws.com. [Video description ends]

That's basically a DNS name that points to our database instance running in the Amazon Web Services Cloud, and it's listening by default on the standard SQL Port, which is 1433 over TCP.

Notice also over on the far right under Public accessibility, it's set to Yes. Now, the default value for that is private accessibility. In other words, Public accessibility, No. So you would have to be, for instance, VPNed into the AWS Cloud in order to be able to manage the database instance. But here it's publicly accessible, so I'm good to go for my on-premises machine running SSMS.

So I'm going to fire up that tool from my Start menu since I've already downloaded it and I've already installed it. Now, I'm presented with the Connect to Server screen where the Database Engine is what's been selected, and I've specified the Server name, that's the endpoint that I just copied from my RDS config. The authentication is SQL Server Authentication, not Windows or Active Directory.

The default username when I deployed that database was set to admin and I've specified the Password. Let's go ahead and connect by clicking Connect. OK. And at this point I am now connected in the AWS Cloud to my Microsoft SQL Server RDS instance. [Video description begins] The Object Explorer pane, which was previously empty, now displays database-1, with it's internal folders: Databases, Security, Server Objects, Replication, PolyBase, Management, XEvent Profiler. [Video description ends] So if I were to expand Databases on the left, go into System Databases, we have all of the normal behavior that we would have if this were an on-premises SQL Server.

If we go to Security, go down to Logins, we'll have the same type of thing we would normally see for SQL-based logins. There's the admin account we logged in with, by the way. So while we don't have access to the underlying server operating system, we do have access, of course, to SQL database objects. Otherwise what would the point be?

So at this point, it's a database design issue, depending on how the database is being used to support an app of some kind, or whatever is going to be stored in the database. That would determine how we would then drill down into our specific databases, and then perhaps examine existing Tables, view stored procedures, or, of course, right click and build New objects as required.

Back here in the RDS console, in the Databases view, if we refresh our database, we could then start clicking on things like the Current activity sessions, which takes us really into the Performance Insights for the database, very valuable information. You can even use this to establish a baseline of normal activity over time.

So we have things like Database load, you can select the Chart type that you want to use to monitor this type of information. You can go to Top users to see who's been using most of the processing time on the server, perhaps by issuing long, complicated queries. Let's go ahead and change the public accessibility option to verify that it does have the impact we think it will, which means we shouldn't be able to connect from SQL Server Management Studio.

So if we go back to my database listing on the left, click on that database identifier, and click Modify, and then scroll all the way down under Additional configuration under Certificate authority, it's currently Publicly accessible. I'm going to choose Not publicly accessible, and it tells me that EC2 instances and other devices outside of the VPC where this database was deployed will not be able to connect to it.

So you could still remote into an EC2 instance in that same VPC. So I'm going to go ahead and scroll all the way down to the bottom and in the bottom right I'll click Continue. We have a summary of our modifications about Public accessibility. Now, we want to watch this Scheduling of modifications. When do we apply this change? The default is to apply it during the next scheduled maintenance window.

And we have a date and timestamp showing when that will be. Or we could choose to apply it immediately. The reason maintenance windows are used is to limit the amount of disruption; background maintenance like config changes, the application of patches, will have against a live, running production database. So Apply immediately, Modify DB instance.

And it says it successfully modified it. If I click back on that database identifier, down under Networking it's important to note the VPC it was deployed into, the default VPC in this case. So that means that you would have to have instances deployed somewhere in there, in these subnets, in order to make a connection if it's not publicly accessible.

And you might have to go back and refresh the view and then click on it to open it again, for some of these changes to actually show up here, such as Public accessibility now reflecting No. OK. So I'm going to Disconnect here in SQL Server Management Studio and try to reconnect once again, and try as it may, we'll not make a connection, because it's no longer publicly visible.

The other thing to bear in mind is that while we can go to the Actions menu to Stop, Reboot, and Delete database instances, if you know you're going to need RDS database compute power for at least a year or more; for the long term, you need it running 24/7, you should consider the use of Reserved instances.

When you purchase reserved database instances, you can realize a large cost saving as compared to running them on demand, all of the time, the way we're doing it right now. So think about then what the workload requirements are for the database, and whether it makes sense or not to use reserved instances to reduce database costs.

10. Video: Deploying DynamoDB (it_clasaa22_02_enus_10)

deploy and configure DynamoDB
[Video description begins] Topic title: Deploying DynamoDB. Your host for this session is Dan Lachance. [Video description ends]
In this demonstration I will be deploying DynamoDB using the AWS Console. DynamoDB is a basic key-value storage solution that can run at a very large scale. In other words, it's a NoSQL type of database solution, it doesn't have a structured schema, unlike if you were using RDS and using MySQL or Oracle.

So DynamoDB is designed for enormous workloads and very quick response times when searching for items that it stores. It's also designed to scale automatically to handle peak workload times. So here in the console, in the search field at the top I will search for dynamoDB and I will select it.

Now, this is a managed service, much like most offerings in RDS, meaning you don't have to provision a server, you don't have to provision the database software, you don't have to patch the OS or the database software, that's handled automatically. Now, getting started with DynamoDB means defining a table structure, but it's nothing like a rigid schema that you would experience with a relational database system like Microsoft SQL Server or Oracle.

For instance, I'm going to go ahead and click Create table. First thing we have to do is enter a name for the table. OK, customers. What's the Partition key? This is the primary key. And that, of course, stems from the parlance available in standard relational database terminology. Let's say custid, the customer ID.

We can select the appropriate data type here, but it's going to be String, but we can also add a secondary component for the primary key, called the Sort key. Anything you would be searching or sorting on often, let's say, searching, let's say the way, we're going to use our customer database, is that we'll often search for people's accounts based on their mobile phone number.

So maybe I'll create a Sort key called mobilephone, and again, I'm going to leave that as a String value. Now, down below it's set for the default Table settings. We want to see some of those options so I'm going to choose Customize settings. You can select a DynamoDB class for Standard-IA that's infrequently accessed, if the data isn't accessed all of the time.

The benefit here is reduced monthly charges. You can also open up the Capacity calculator, which is great, because we know that database capacity planning is paramount in determining the success of the performance of your backend databases, while minimizing cost. So here we could specify the Average item size, number of reads and writes per second, to the point where we get a sense of how many Read and Write capacity units we should configure our database with, along with an estimated monthly cost.

So down below, if we want to use those recommended read and write capacity units, that's how we can provision the database or it can simply be On-demand much like when you fire up an EC2 instance and you pay for it while it's running. Of course, you would still always incur storage charges even if the database isn't running.

So I'm going to leave Read capacity Auto scaling On. NoSQL databases are designed to scale at a massive level. I'll leave the default minimum and maximum capacity units of 1 and 10 with a Target utilization of 70%, and I'll leave the same settings for Write capacities. Of course, depending on the nature of your app, you might have a lot more reads if it's a heavy querying type of usage application.

And if I want to create Secondary indexes on other data items that are not part of my primary key, I can do that. Down below, for encryption of data at rest, if we are mandated perhaps by regulations to have control of encryption keys, we could use the option where we have keys stored in our account that are owned and managed by us, as opposed to having variations on Amazon or AWS managed keys, but I'll leave the default for that [Video description begins] The default option is: Owned by Amazon DynamoDB. [Video description ends] and I'll click Create table.

OK, before we know it, it's been deployed. So we've got our customers DynamoDB table shown in the list here with a Status of Active. It also reflects our Partition key configuration and our Sort key configuration. The S in parentheses, of course, is string that represents the data type. And we've got read and write capacity mode enabled with auto scaling. [Video description begins] The other tabs on the table read: Indexes, Size, and Table class. [Video description ends]

If I click on the customers table link to open up the details for it, this is where we'll have some general configuration information as well as some standard table metrics related to reading and writing of items in the table. But up at the top I can choose to Explore data items where the item is actually like the row or the record equivalent of what you would have in a relational database environment.

So for the customers table over on the right down below the Items returned is 0, because we haven't created any items yet. Now, normally this would realistically be done programmatically, maybe with a web frontend or some kind of data ingestion service, but here in the GUI we can at least get a sense of how it looks and feels.

So I'm going to choose Create item and it presents me with my Attributes, or columns or fields, if you will, so a custid, let's say abc123, and the mobilephone I'll just fill in a fictitious number and I'll choose Create item. [Video description begins] In the Value column of the mobilephone row, the host types 555-555-5555. [Video description ends] And this is basic NoSQL storage.

So now, our item is showing now with a customer ID and a mobilephone item listed. Notice that when you're creating an item, you can also Add a new attribute at that time [Video description begins] The host clicks on Add a new attribute button, to reveal a dropdown menu with tabs: String, Number, Boolean, Binary, Null, String Set, Number Set, Binary Set, List, Map. [Video description ends] such as Boolean, which is a True or False value, let's say a preferredcustomer. Well, that, it's either True or False.

Let's go ahead and add a second customer here and I'm going to set preferredcustomer to True and I'll create the item. [Video description begins] In the Value column of the custid row, the host types "abc456", and in the mobilephone row, he types555-555-5555. [Video description ends] All right, so now down below, we've got our two items. If I open up the second item, [Video description begins] The host clicks onabc456. [Video description ends] notice our preferredcustomer is showing here is a Boolean value set to True. [Video description begins] The host returns to the previous page. [Video description ends]

Up at the top, we can also create a Query. I can click Add filter and I can specify an attribute name, let's say the custid, which is a String value Equal to or perhaps Not equal to, and we have a list of operators available here; Greater than, Between, Exists, Not exists, Contains, and I'll set it to Equal to abc123. And then down below, I'll just go ahead and run the query. Down below, the Items returned, of course, is 1 because we have a customer with that ID.

11. Video: Deploying DocumentDB (it_clasaa22_02_enus_11)

deploy and configure DocumentDB
[Video description begins] Topic title: Deploying DocumentDB. Your host for this session is Dan Lachance. [Video description ends]
In this demonstration, I will be deploying DocumentDB. DocumentDB is a NoSQL type of database offering, a managed database service offering in AWS that's MongoDB-compatible. Anybody that's worked a lot with NoSQL databases will be familiar with MongoDB.

So to get started with this deployment in the console, I'm just going to search for document up in the search bar at the top and I'll choose Amazon DocumentDB. So that takes me into the console for that management where I have to begin by deploying a DocumentDB cluster. So I'm going to go ahead and click the Create button to get that started.

The Cluster identifier is automatically set, [Video description begins] The Cluster identifier field is filled-in asdocdb-2022-07-26-21-29-16. [Video description ends] the Engine version here is set to version 4.0.0, I don't have a reason to change that, and we can also set the Instance class, in other words, the instance type or the sizing for our database deployment. I'm going to reduce it down to 2 vCPUs and only 4GB of RAM. [Video description begins] The host selects db.t4g.medium from the dropdown menu under Instance class. [Video description ends]

Because we're defining a cluster, we can define how many instances we want deployed in that cluster. So naturally, this is designed for large scale uses of data that will be stored in the NoSQL database. [Video description begins] The Number of instances is set to 3. [Video description ends] For Authentication, I'll specify a Master username, in this case of mbishop, and I'll specify and confirm the Master password.

I can also go down and turn on advanced settings so I can see the VPC affiliation for this database deployment, the cluster Port number, which is 27017 by default, the fact that Encryption-at-rest is enabled by default, I can select the key used for that encryption. [Video description begins] The host selects (default)aws/rds from the dropdown menu under Master key. [Video description ends] We have some Backup retention details we can specify, but I'm not going to change any of those items.

I'm just going to go down to the very bottom and I'm going to choose Create cluster. And after a moment we're placed into the Clusters view where our Cluster identifier is shown along with the three nodes that we specified. So if I click on the Cluster identifier itself to go into its properties, the Cluster status is currently showing as being Available, one of three instances are available, because it's still initializing.

Down under Connectivity & security, this is important information, the first thing is to download the Amazon DocumentDB Certificate Authority which you're going to need if you're going to make an authenticated connection to the cluster. So the URL is shown here along with using perhaps wget if you're on a Linux host, but you might be on a Windows host.

You're going to need that. It then talks about using mongo shell because DocumentDB is Mongo-compatible. So we have the command line or the connection string for mongo and this is actually specific to our deployment, so the name is correct, we have to have brought down the DocumentDB CA, the username is correct here, mbishop, we would specify our password of course.

If you want to connect with an app to the cluster, then we have the mongodb command line shown for that. Now, this is more on the database administrator or developer side, but if you want to get into that type of connectivity where you can actually start to manipulate data stored in DocumentDB and query it, you could download the MongoDB Shell. Now, the MongoDB Shell is even available for the Windows platform. [Video description begins] The host switches tabs to AWS Cloud9 interface. On the left-hand side, there is a vertical menu with tabs: Your environments, Shared with you, Account environments. The Your environments tab is currently selected. [Video description ends]

Or if you're a developer and you're using AWS Cloud9, you could Open your IDE, and within there you could install the Mongo Shell. [Video description begins] The host returns to the Amazon DocumentDB page seen previously. [Video description ends] But back here in the console, if I go back to my cluster details, I can go to Instances and the three individual instances are shown here, one being the primary, the others being replica. So when we make a connection to the cluster, given the connection string that was provided, we're going to be connecting to the primary node in that cluster.

We can click on any of these individual cluster nodes to get details about them, such as connection strings for connecting to that specific instance. We can also go to the Configuration tab to see the VPC association for where that instance was deployed. And of course the Username is shown as mbishop as per our configuration, and the Port is 27017.

And straight from the Amazon documentation for DocumentDB, I'll just zoom in a little bit, we start to get a sense of the syntax that we would use to start inserting documents into the database on the singular or individual document level, or how to insert many all at once, using db.profiles.insertMany.

And further down, the syntax is shown for how we can start searching for specific data using db.profiles.findAndModify. So at this point we get to where database admins that are specifically familiar with MongoDB-compatible databases and developers, would work together to build the logic for getting data into and out of DocumentDB.

12. Video: Creating Elastic Block Store (EBS) Volumes (it_clasaa22_02_enus_12)

create an Elastic Block Store (EBS) volume
[Video description begins] Topic title: Creating Elastic Block Store (EBS) Volumes. Your host for this session is Dan Lachance. [Video description ends]
In this demonstration, I'm going to create an EBS volume. EBS stands for Elastic Block Store. You can think of it as being a virtual disk that we can then use with EC2 instances by attaching the volume to it, after which it shows up as just another mass storage device as if you had a physical server and had physically plugged in some storage, meaning that you will have to initialize the disk, you'll have to partition it, you'll have to format the partitions just like you normally would.

The difference is that it's an object or a resource in the Amazon Web Services Cloud. To get started here in the Console, I'm going to go to my Recently visited and click EC2 to go to the EC2 Management Console. If I were to go to my Instances view, from here I can click on an instance and go all the way down to the Storage tab to check out its storage.

For example, here we've got an EBS Root device type that contains the operating system and the Root device name is shown here as /dev/sda1, which is standard Unix and Linux nomenclature for disk devices. So it's shown down under Block devices, which is a section I can expand or collapse with the size of the volume; 30 GiB.

And the Attachment status, of course, is it's Attached to the virtual machine that we are looking at the properties of here. I even have an attachment date and timestamp for that. However, in the left-hand navigator I have an Elastic Block Store section where I can click on Volumes. [Video description begins] A table displaying 12 Volumes and their details is shown. It has a selectable column, followed by columns: Name, Volume ID, Type, Size, IOPS, Throughput, Snapshot, Created, Availability Zone, Volume state, Alarm status, Attached Instances, Volume status, Encryption, KMS key ID, etc. [Video description ends] Any existing EBS volumes will be shown here and as I scroll over to the right we've got a Volume state column that will tell me, whether or not the EBS volume is in use.

They're all showing here as being In-use, and under the Attached Instances column we can see the instance ID to which those volumes are attached. But what I'm going to do here is click Create volume. Now, when you're creating an EBS volume, you can select from General Purpose SSD, whether it's gp2 or gp3, the difference being gp2 does not let you modify the IOPS, you don't get to specify that value, but gp3 does.

The IOPS is the input output operations per second. In other words, a disk throughput measurement, which is very important if disk latency tends to be a problem with a given workload. If there's a lot of read and write activity. I can also go to Provisioned IOPS SSD 1 and 2, depending on what I need for performance, such as a maximum value of IOPS, up to 1000 IOPS per GiB of storage.

So we can also specify the size here of course in the Size field. And depending on what your needs are, you also have Magnetic disks or Cold Hard Disk Drive storage for infrequently accessed data. The older hard disk magnetic storage technology, HDD, Hard Disk Drive, is slower and thus doesn't perform as well for any workloads compared to SSD, but depending on what you're doing to save on costs, perhaps testing, and disk I/O is not of the utmost importance, you might select one of these.

I'm just going to leave it on General Purpose gp2. Now, I am in the North Virginia us-east-1 region as shown in the upper right here, and so I can select the Availability Zone where I want this volume to be deployed. Under Snapshot ID I can also choose to create this volume [Video description begins] The host selects us-east-1a from a dropdown menu under Availability Zone. [Video description ends] based on an existing volume's snapshot.

It's kind of like having a disk image to start from, but I'm not going to create it from a snapshot, I'm going to create an empty new EBS volume. I can also choose to Encrypt this volume where I can then select a KMS key, a key management services key. KMS is a cloud-based AWS service where you can generate and manage keys.

So I can use the default AWS EBS key for that and of course I can add Tags down at the bottom, up to 50. I'm going to add the Name tag and I'm going to call it WindowsDataVol1, and down at the bottom right I'll then click Create volume. OK. So it's created our new volume. If I kind of, OK, so if I refresh the view, my WindowsDataVol1 should show up way down at the list.

There it is. So I can click on the link for the volume to open up its details at any time. Here I have the Volume ID it was assigned by AWS, the Volume state, which is currently Available, the KMS key that's used to encrypt it, the Size, the amount of IOPS, and the creation date and timestamp, that type of thing.

I can also go down under Monitoring to check out things like read and write bandwidth, read and write throughput, if I'm really concerned about the performance at the disk I/O subsystem level. But if I go back to the Volumes view, I can put a checkmark to the left of that EBS volume, and under Actions I can choose to modify some aspects of it, such as the Volume type or the Size.

I can also go back to the Actions menu and create a snapshot of that EBS volume. I'll just call it Snapshot1. A snapshot is like a point-in-time picture of the current state and data of that volume, and you could use that as a backup source. So I'm just going to go ahead and create the snapshot, which of course, as you might guess, will show up in the Snapshots view.

So there's Snapshot1. And I could select the snapshot, go to Actions and even Create a volume from it, Archive it for long-time storage, Delete it. But I'm going to go back to the Volumes view yet again, put a checkmark in front of WindowsDataVol1 and under the Actions button, here we're going to choose to, here I can choose to Delete the volume, I can also choose to Attach the volume.

And because we decided that we were going to encrypt this volume, there's a message that states it can only be attached to an instance type that supports EBS encryption, but I'm going to go ahead and Cancel that. Now, bear in mind that when you are in this view, remember that you can check out the Volume state column, you can sort by it by clicking on it if you so choose.

Now, this can be important because if you have numerous available EBS volumes that are not needed, it becomes a cost issue. You are paying for something that's not needed, that exists, that is not being used. So bear in mind you want to watch out then, for EBS volume sprawl.

13. Video: Attaching Volumes to EC2 Instances (it_clasaa22_02_enus_13)

attach an Elastic Block Store (EBS) volume to an Elastic Compute Cloud (EC2) instance
[Video description begins] Topic title: Attaching Volumes to EC2 Instances. Your host for this session is Dan Lachance. [Video description ends]
We know that we can create EBS volumes in the AWS Cloud, that we can then basically treat as virtual disk devices that we can then attach to EC2 instances. And when we do that, that shows up as a new disk device in the virtual machine operating system. And so you would treat it as a regular disk device.

You would initialize the disk, you would partition, you would format it, copy data to it, set permissions to files and folders as you normally would. The only difference is this is a managed service in the cloud. And so we're going to go ahead and attach an EBS volume to an EC2 instance. Why don't we start here in the console by going into the EC2 Management Console?

Let's go to the Instances view, and let's open up an existing instance and poke around for a moment at its storage. [Video description begins] There is a horizontal menu with tabs: Details, Security, Networking, Storage, Status checks, Monitoring, Tags. [Video description ends] Down down below I'll click the Storage tab. Every EC2 instance is created from some kind of machine image that has an operating system.

So we've got a Root device EBS volume for the OS, we've got a Volume ID here, it's about 30 GiB in size, and of course it's attached to the EC2 instance we happen to be looking at the properties of. If I click on that Volume ID [Video description begins] The Volume ID reads: vol-0a8cd59eb770dc26f. [Video description ends] it takes me into a filtered view for EBS volumes, that's really where it placed me here, in the Volumes view under Elastic Block Store, and there's the volume.

If I click on it again, I have all of the details. So it's a gp2, 100 IOPS, 30 GiB disk, not encrypted because there's no KMS key information. Of course, over on the right under Encryption it also says Not encrypted. Well, that's a good indicator. [Video description begins] There is a horizontal menu with tabs: Status checks, Monitoring, Tags. The Status checks tab is currently selected. [Video description ends]

And down below the Volume status and the I/O status are both looking good and Enabled, and if I go to Monitoring this is where I might choose to look at some of these metrics for read and write throughput, read and write bandwidth, the average queue length where queuing up items for a long period of time is bad news. It means your underlying disk I/O subsystem is too busy to deal with disk requests, so it's queuing them up.

We also have average read and average write size when it comes to data, so this can be extremely valuable. However, if I go back to the Volumes view, I've got a volume here called WindowsDataVol1, and if I just stay in this view and scroll over to the right, under the Volume state column it states that that is an Available EBS volume.

In other words, it's not attached to an instance. So I'm going to put a checkmark next to it and under the Actions button I'm going to choose Attach volume. So it says that this is an encrypted volume and so you can only attach it to an instance that supports EBS encryption.

So from the Instance dropdown list, so from the Instance dropdown list I could choose the instance I wanted this to be attached to, the Device name is generated automatically and I could just choose Attach volume. [Video description begins] The field under Instance is filled in as:i-0b0915c199d4d17c6 and the Device Name is set to/dev/sdf/. [Video description ends] Once I've done that, that data volume will now show over on the right as being In-use with the link to the instance ID. Let's go ahead and create another volume.

I'll leave the defaults here for SSD gp2, 100 GiB, and I'll just go ahead and Create volume so it shows up at the top of the list here. I'm just going to click right in the Name column and I'm going to call this WindowsDataDisk2 and I'll click Save.

Now, this one is not encrypted so if I select it and go to Actions and then choose Attach volume, I don't get that note, about the instance having to support EBS volume encryption, but notice my list of instances is very tiny. Where are they all? I know I have many more. Well, there's a note that tells us exactly what's going on.

It says, only the instances in the same Availability Zone, which in this case is us-east-1a, as the selected volume will be shown. OK. Well, let me Cancel out of that. If I select that disk volume and go to Actions, Modify volume, if I go to my Instances view, and let's say I'm interested in my WindowsServer2022-1 virtual machine;

I'll just click on the Instance ID to get some details. If I go down under the Networking tab, notice that this is in an Availability Zone called us-east-1b. Well, no wonder it's not showing up as an instance I can attach the volume to. So I'm going to go back to Volumes, create another one, but this time I'm going to change the Availability Zone to us-east-1b.

I'm going to go ahead and create the volume, so it's vol-0c2 is part of the unique name, so that's shown here in the list. I'm just going to go ahead and edit it in line and call it WindowsDataDisk3. Now, this time when I have it selected and go to the Actions menu; now Attach volume is grayed out, let's just refresh the screen, it was just created.

Let's try that again. There we are. We can now attach volume. When we go to our Instances view, now we have a different list, because the Availability Zone matches. Not every service is like this in AWS, but some are. So I'm going to select my WindowsServer2022-1 and I'll go down at the bottom and click Attach volume.

So if we go back to our Instances view, check out the details of that instance and scroll down under the Storage tab, notice that we now have two volumes shown. The one we've just attached is the 100 gigabyte one. Just going to go at the top here and click Connect, RDP client, I'm going to Download remote desktop file to connect to it, I'm going to get the password by decrypting the password with my Windows key pair file, which I have on my machine, I'll click Decrypt password, there we are.

I'll copy the password and I'll click the RDP file. I want to open a remote connection because I want to see what that disk looks like within the OS. The answer is it's going to look like any disk within the OS. It's not going to be any different than anything you would have encountered before if you're already familiar with disk management in that OS. [Video description begins] The Administrator: Windows PowerShell interface is shown on-screen. [Video description ends]

So for instance, here in my Windows Server environment, if I search for disk, and if I choose Create and format hard disk partition, it starts the old Disk Management utility. There's more than one way to do this, but there's my 100 gigabyte disk. I could right click on it and nothing's available because over on the left it's offline.

So over there I'll right click and choose Online. Then I can right click on the disk over there on the left again and choose Initialize Disk, let's say it's GPT, so we can have more than four partitions. OK. There we go. Now I can right click on it, let's say, and just build a simple volume and just accept all of the defaults. It'll format it as NTFS, it's drive letter D, it's just another mass storage device at this point. But that's important to know when it comes to attaching EBS volumes to EC2 instances.

14. Video: Configuring Elastic File System (EFS) (it_clasaa22_02_enus_14)

create a Network File System (NFS) configuration and mount from Linux
[Video description begins] Topic title: Configuring Elastic File System (EFS). Your host for this session is Dan Lachance. [Video description ends]
All right. In this demo, I'm going to be configuring Amazon's Elastic File System or EFS. What this really is, is a variation of cloud-based storage so it's not the same thing as an S3 bucket. But what it's designed to do is be a file system that you can remotely connect to and mount, so in other words, using the old network file system or NFS protocol that has long been used by Unix and Linux.

It can also be used by Windows if you have the right software installed, but allows for the reading and writing of files in the mounted target. So to get started here in the console, I'm going to search for efs and I'll choose EFS to go into that management console. [Video description begins] The Elastic File System Console interface is shown on-screen. On the left, it has a vertical menu with tabs: File systems, Access points. [Video description ends] Now, I don't have any File systems defined yet, so I'll click on the File systems view on the left.

We'll begin by clicking on Create file system. For the Name, I'm going to call it projects. Now, I know I've got a number of EC2 instances deployed into my default VPC and so therefore I'm going to associate my EFS configuration with that same VPC. I'm going to leave it on Standard for the Storage class, which allows me to have more high availability and durability than I would have with just a single Availability Zone.

So I'll leave that on and I'll choose Create. OK. And after a moment, it's done. So we now have a listing called projects in this case for my file system. Notice by default it is Encrypted. I can click directly on the name of the project to open up its details, to read its configuration settings, to monitor various aspects of the performance of the Elastic File System. [Video description begins] There is a horizontal menu with tabs: Metered size, Monitoring, Tags, File system policy, Access points, Network, Replication. The host selects File system policy tab. [Video description ends]

I can edit a file system policy, for instance I might want to Prevent root access. When I select that checkmark, it actually puts in the JSON equivalent over on the right for my file system policy. I'll just scroll down at the bottom right and click Save.

Under the Network column, I have a number of available Mount targets shown here with the target ID as well as the IP address, and I can go to Replication up at the top and I can create a replica of my EFS file system by specifying a target region. But I'm not going to do that, I'll choose Cancel.

Now, when I'm in the properties of my EFS config, notice I've got an Attach button in the upper right. This is important because it contains the instructions on how to make a connection, how to mount the mount target, such as from a Linux host, whether I want to mount using the DNS name or mount via the IP address. So the entire command is provided.

It's using sudo to run a privileged command, mount -t for the file system type of nfs4, and then we've got a number of options followed by the IP address of the mount target and the local mount point, which would be an EFS folder that we want to mount it in. [Video description begins] The IP address reads: 172.31.6.176. [Video description ends] I'm going to actually copy that.

I'm going to use the free PuTTY tool to make a connection to an Amazon Linux EC2 instance I already have running in the AWS Cloud, and I'll click Open. So I'll Accept that unique fingerprint for that host, I trust it, the default username for Amazon Linux instances is ec2-user. OK, and I've authenticated with public key authentication. So here in Amazon Linux if I type pwd for print working directory, it reports that I'm in my ec2-user home directory.

So I'm going to run mkdir and I'm going to make a directory called efs. Now, that's important because if I paste in the copied command, it assumes that I have a mount point forward called efs that I would go into in my local file system in Linux to gain remote access to my Elastic File System. I'm going to go ahead and press Enter to run that mount command. Now, once the mount completes that remote EFS file system is available locally under efs and unless the policy prevents it, we have read and write access to it.

15. Video: Course Summary (it_clasaa22_02_enus_15)

summarize the key concepts covered in this course
[Video description begins] Topic title: Course Summary. [Video description ends]
So in this course we've examined which AWS services should be used for data transfer, which database configurations best support a given workload, and how to manage EBS and EFS. We did this by exploring AWS Transfer and Snow Family services, and how to create an AWS Snow Family job. We then got into AWS database capacity planning, deployment, and management of MySQL in AWS.

We then deployed and managed Microsoft SQL Server running in AWS, we deployed DynamoDB and DocumentDB solutions, and finally we worked with EBS volumes in terms of creating a volume and attaching it to an EC2 instance, followed by configuring the elastic file system, EFS. In our next course, we'll move on to deploy and manage S3 buckets. We'll create them, we'll manage them, as well as objects within them, we'll manage storage tiers as well as when to use the storage gateway, as well as the CloudFront content delivery network.

© 2023 Skillsoft Ireland Limited - All rights reserved.
