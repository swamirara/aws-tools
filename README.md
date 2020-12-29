# aws-tools
AWS Cloud Useful Tools 

*********org-formation*******
https://github.com/org-formation/org-formation-cli

This is arguably the most impressive and useful open source tool I have seen in a while. 
Org-formation is a CLI tool that lets you manage your entire AWS organization using Infrastructure-as-Code (IAC). 
It sports an AWS CloudFormation-like syntax and has more than 50 features, including:

Create new AWS accounts in code.
Create AWS organizational units (OU) and adding accounts to them.
Define Service Control Policies (SCPs), configure cross-account AWS CloudTrail collection, etc.
If you have an existing AWS Organization, you can run org-formation init to pull them into a template so you can start managing them with org-formation going forward.
You can use org-formation update-stacks to apply CloudFormation templates to multiple accounts and regions.
You can use pseudo-functions such as **!Ref**, **!GetAtt**, and **!Sub** at the AWS Organization level as well as to reference accounts, regions, and organization units.
You can use the org-formation init-pipeline command to bootstrap a CI/CD pipeline with AWS CodeCommit and AWS CodePipeline to automatically deploy updates to your AWS Organization.

*********lumigo-cli*********
https://github.com/lumigo-io/lumigo-cli
The lumigo-cli is a Swiss army knife of helpful commands for working with AWS. There are a few commands that are especially useful if you do a lot of work with Lambda.

For example, you can run lumigo-cli list-lambda to list all your functions in all regions; it gives you a complete overview of what you have in your account and can help you quickly identify inactive functions (i.e. functions that haven’t been invoked in more than 30 days).

example output of inactive functions

The analyze-lambda-cold-starts command analyzes the cold start performance of your functions in all regions, including their Provisioned Concurrency utilization. T
his helps you identify functions to optimize for better cold start performance, or to enable Provisioned Concurrency on them.


example analysis of cold start performance of functions

To apply a data-driven approach to finding the best memory setting for a function, use the powertune-lambda command 
to find the best setting for performance, cost, or a balance of the two.

example output of best setting for performance, cost, or a balance of the two

If you use Lambda with SNS, SQS, Amazon DynamoDB, or Kinesis streams, then seeing what events your functions are triggered with can be challenging sometimes. 
The following commands let you tail these event sources and see what actually is going on:

lumigo-cli tail-cloudwatch-events-bus
lumigo-cli tail-cloudwatch-events-rule
lumigo-cli tail-dynamodb
lumigo-cli tail-eventbridge-bus
lumigo-cli tail-eventbridge-rule
lumigo-cli tail-kinesis
lumigo-cli tail-sns
lumigo-cli tail-sqs

If you work with lots of different accounts or profiles, then you will appreciate the whoami and switch-profile commands. 
They allow you to identify what profile you’re currently using and quickly switch to another.

example view of switching users

All in all, there are more than 20 commands, with something for nearly everyone.

https://aws.amazon.com/blogs/opensource/24-open-source-tools-for-the-serverless-developer-part-1/#:~:text=Many%20open%20source%20alternatives%20are,AWS%20Lambda%20deployment%20frameworks%20compared%E2%80%9D.

*******Cloud Tracker******
CloudTracker helps you find over-privileged IAM users and roles by comparing CloudTrail logs with current IAM policies.
https://github.com/duo-labs/cloudtracker

*******Cloud Tracker******
Open-source application to programmatically delete AWS resources based on a whitelist and time to live (TTL) settings
https://github.com/servian/aws-auto-cleanup

RepoKid
https://github.com/Netflix/repokid 
Repokid uses Access Advisor provided by Aardvark to remove permissions granting access to unused services 
from the inline policies of IAM roles in an AWS account.

*******PacBot******
Policy as Code Bot (PacBot) is a platform for continuous compliance monitoring, 
compliance reporting and security automation for the cloud.
https://github.com/tmobile/pacbot


*******TruffleHog******
github.com/dxa4481 | CloudFormation
TruffleHog Searches through git repositories for secrets, digging deep into commit history and branches. 
This is effective at finding secrets (such as AWS Secret Keys) accidentally committed.


*******cloud-nuke****** Cation: Destructive
github.com/gruntwork-io | AWS
A tool for cleaning up your cloud accounts by nuking (deleting) all resources within it.

cloud-nuke was created for situations when you might have an account you use for testing and need to clean up 
leftover resources so you're not charged for them. Also great for cleaning out accounts with redundant resources. 
Also great for removing unnecessary defaults like default VPCs and permissive ingress/egress rules in default security groups.


*******Komiser******
github.com/mlabouardy | AWS
Komiser is a tool to analyze and manage cloud cost, usage, security, and governance in one place. 
The tools helps stay under budget by uncovering hidden costs, monitoring increases in spend, 
and making impactful changes based on custom recommendations.
**It can show the service limits in it's webportal.
