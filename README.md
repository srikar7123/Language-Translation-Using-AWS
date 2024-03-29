![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/c49a2241-0d33-4c86-8d7e-793c6ae05473)

# Language-Translation-Using-AWS Serverless Services
Language translation is the process of translating text or speech from one language to another in order to facilitate communication between speakers of different languages. Translation is essential for many aspects of daily life and business, such as assisting international travelers, allowing businesses to access foreign markets, providing customer support for multilingual audiences, and making it easier for speakers of different languages to access healthcare and education. Translation also improves cross-cultural understanding, encourages global collaboration, and promotes inclusivity by removing language barriers.

Using AWS services like Lambda, S3, CloudWatch, and Translate, you can create a system that automatically translates text stored in an S3 bucket and logs the translation activity using CloudWatch.

1)AWS Lambda- With the serverless computing service AWS Lambda, you can run code without having to setup or manage servers.

2)S3(Simple Storage Service)- Object storage designed to store and access any quantity of information from any location.

3)AWS Translate- With Amazon interpret, you can interpret and analyze vast amounts of text to foster cross-lingual user conversation as well as localize content for a wide range of international consumers.

4)CloudWatch- CloudWatch is an AWS resource monitoring tool that offers statistics and useful insights.

5)IAM Role- One service that assists you in securely managing access to AWS resources is called Identity and Access Management, or IAM.

In this article, we will discuss how to use these services to change the language in various domains. Step 1: Creating AWS S3(Simple Storage Service). 1)In the AWS console search for S3 in the search bar and select the service. 2)click on Create bucket. 3) Allocate a unique name to your bucket 4)Make sure you enable versioning  5)Give a suitable name for the bucket and click on Create bucket. 6)The bucket will be created.

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/ab369c3c-5ae2-4c36-8059-21bce1133c08)

Note- Create a two buckets (inputbucket,outputbucket)
Step 2: Creating IAM Role. 1)In the AWS console search for IAM in the search bar and select the service. 2)In that select roles and click on Create role. 3)Select use cases as Lambda and click on next. 4)In permission, policies choose CloudWatchFullAccess S3FullAccess and TranslateFullAccess and then click on next. 5)Give a suitable name for the role and click on Create role. 6)The role will be created.

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/ecd0d6de-85b6-43fb-a8f5-c807110ccce7)

Step 3: Creating Lambda Function 1)In the AWS console search for Lambda in the search bar and select the service. 2)Provide the name of the function. 3)In the position of runtime, we must choose the language that we want. Here, I am choosing the most recent python 3.9 version. 4)Choose whether to create a new or existing role as the executing role in the following step. I’m choosing the role that I already created in the previous phase. 5)Rest everything. We can keep it optional 6)Select Create a Function.

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/3ce76e2a-83dc-4f87-9265-7cdbe8e1f867)

Step 4:After the creation of the lambda function , we need to add the Trigger 1)click on Add Trigger. 2)search bar will be appear. 3)Type S3. 4) Add S3 And click choose/click the Add trigger.

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/f93a1139-4045-4c4c-8288-881b02971659)

Step 5: Deploy the Lambda code .1)We need to write Lambda code to change the language 2)Next, choose to configure a test event 3)Give a suitable name for the test event and click on create.

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/fb0c5f23-78a4-490a-b66f-32759c07faee)


Step 6: Check  CloudWatch Logs.1)In the AWS console search for CloudWatch in the search bar and select the service. 2)In the left navigation pane, Click on logs to check the logs. health checks ,and monitoring the error handling .3)If any errors. change the code in lambda function which you created .4)If no errors go to next step.

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/a1c913b3-c560-473d-822e-0db4690c1051)

Step 7: Go to AWS S3. 1)Click on 1st Bucket (Input bucket).2)click on Upload. 3)Upload the any .txt document /drag the .txt document. 4) click on Upload 5)After Uploading the document go to back and open the 2nd bucket(Output bucket). 6)Which is uploaded in input bucket will come to output bucket by the lambda function with translation of language

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/1a9ac62e-da20-4808-8bc8-e6f0b6bbfde0)

Step 8: Opening Output Bucket(2nd bucket). 1)Click on output bucket. 2) There is an one .txt document. 3) click on the document .4) It shows Open or Download .5) Click Open. 

Result :

![image](https://github.com/srikar7123/Language-Translation-Using-AWS/assets/110438502/012ec960-6b32-4849-928b-e0183176df3a)

Conclusion:
By concluding this article, using AWS Lambda, AWS S3, IAM role, CloudWatch, and AWS Translate we can change the languages in various domains. You may effectively translate text material, automate the translation process, keep an eye on system performance, and guarantee scalability by adhering to the specified procedure. Making use of AWS services' features provide a reliable and affordable option for language translation projects. You may build a trustworthy translation system that satisfies your project needs with the right configuration, testing, and optimization.




