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

On the right-hand side of the screen, in the Target section, add a target by clicking on Add target.
In the drop-down, change Lambda function to SNS topic.


![image](https://user-images.githubusercontent.com/40290711/170548149-b9d62dde-9618-4ef0-a89b-f21967bc51c7.png)

