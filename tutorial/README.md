## Launch Your First Stack ##

AWS CloudFormation allows us to spend less time managing minute details of 
AWS resources and more time focusing on our applications running in the cloud.
A CloudFormation template in .yaml or .json formats can provision all of your
necessary cloud infrastucture and automate the deployment of these resources
across all regions and accounts in a reproducible way. These simple templates
allow us to effectively version our environment. This is useful to both track
changes over time, and efficiently delete and re-create resources. 

This is referred to as Infrastructure as Code (IaC).

In this example, we will use a .yaml CloudFormation template to describe, 
create, and provision IAM roles that can be used with AWS Batch. 

### To Begin ###
* Read through the template file for iamRoles.yaml, referring to the 
documentation for more details: 
    * https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html
* Login to the AWS Management Console and navigate to the Service page for 
CloudFormation.
* Select "Create Stack."
* Copy iamRoles.yaml into a space in s3 (e.g. s3://bucketname/user/yourname/)
* Use the S3 https URL for the above as the template URL and hit "Next"
* Enter in a Stack Name (e.g. NoorasFirstStack)
* Supply the parameter in our template for s3 bucket (e.g. bucketname)
* Click through the next few pages,  hit "Next", check the acknowledgement,
then "Create Stack"
* You can monitor in real time what stage your stack is in. Use the refresh
icon to see all stack events. 
* In our example, we created an IAM role and an IAM policy. Navigate to Service
page for IAM, hit "Roles" then "Policies" and see that your resources 
were generated successfully.
    * The IAM role you created will be named "STACKNAME-ROLENAME-STR"
    * The IAM policy you created will be named "STACKNAME-POLICY-STR"
* After you look through the details, go ahead and navigate back to the
Service page for CloudFormation. Select your stack and "Delete Stack" to
rollback the resources you just created.

## Other Examples ##
* Here's an example of a nested stack courtesy of AWS Support Engineer, Kairavi:
    * LambdaRole.yml
    * NestedStackReference.yml

