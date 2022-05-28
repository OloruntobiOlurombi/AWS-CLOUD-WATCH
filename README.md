# Topic: AWS-CLOUD-WATCH

### Overview 
> Amazon CloudWatch is a monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), IT managers, and product owners. CloudWatch provides you with data and actionable insights to monitor your applications, respond to system-wide performance changes, and optimize resource utilization. CloudWatch collects monitoring and operational data in the form of logs, metrics, and events. You get a unified view of operational health and gain complete visibility of your AWS resources, applications, and services running on AWS and on-premises. 

### Prerequisites:
> AWS Account
> SNS Topic 

### Tasks
> Create Cloud Watch event to react to the creation of an Amazon EC2 instance
> Send SNS notification via Cloud Watch when an event occurs

### STEPS
- Follow the exercise instructions described below:

### STEP 1: Create CloudWatch Rule
> Navigate to the CloudWatch service.

![image](https://user-images.githubusercontent.com/40290711/170534195-e8d5553c-fe1a-4918-bef4-1aa2acf52ee1.png)

> On the left-hand menu, under ***Events***, select ***Rules***.

![image](https://user-images.githubusercontent.com/40290711/170538008-f14e650f-9589-4292-991d-ea81ca7ff4ce.png)

> Click on the Create rule button.
> For Service Name, select EC2.
> For the Event Type, select EC2 Instance State-change Notification.
> Select the Specific state(s) radio button. Select running from the drop-down box.

- Note: This configures the rule to trigger whenever an Amazon EC2 instance changes to the running state, which happens when an instance is launched or started.

> On the right-hand side of the screen, in the Target section, add a target by clicking on Add target.
In the drop-down, change Lambda function to SNS topic.

> For the Topic, select the topic you created in the SNS hands-on exercise.

- >Important: If the Topic doesn’t appear, the Access policy – optional section doesn’t have the correct permissions to allow other services to access the Topic.

![image](https://user-images.githubusercontent.com/40290711/170803973-f2d6c77b-2f38-4d79-b5d3-ed5e29679dc8.png)

> Scroll down and click the Configure details.
> Enter a name in the Name field. Ensure the state is Enabled. Click Create rule.

![image](https://user-images.githubusercontent.com/40290711/170804115-a88f5d2e-989e-4d6d-9d1e-898b304b920e.png)

