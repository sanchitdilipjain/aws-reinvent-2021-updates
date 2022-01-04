## Amazon S3 Event Notifications with Amazon EventBridge

**What is Amazon Simple Storage Service (S3)?**
- Amazon S3 is one of the main building blocks of AWS. It’s advertised as ”infinitely scaling” storage. It’s widely popular and deserves its own section
- S3 provides unlimited storage space and works on the pay-as-you-use model. Service rates get cheaper as the usage volume increases
- Amazon S3 allows people to store objects (files) in “buckets” (directories). S3 resources for e.g. buckets and objects are private by default

**Amazon S3 Event Notifications with Amazon EventBridge**

- We can now use Amazon S3 Event Notifications with Amazon EventBridge to build, scale, and deploy event-driven applications based on changes to the data you store on Amazon S3. 
- This makes it easier to act on new data in Amazon S3, build multiple applications that react to object changes simultaneously, and replay past events, all without creating additional copies of objects or developing new software. 
- With increased flexibility to process events and send them to multiple targets, you can now more confidently create new serverless applications with advanced analytics and machine learning (ML) at scale without writing single-use custom code.
- We can start sending S3 Event Notifications to EventBridge with a few clicks in the AWS Management Console or with a single API request
- **Benefits**:
  - Use advanced filtering and routing capabilities and send events to 18 targets, including AWS Lambda, Amazon Kinesis, AWS Step Functions, and Amazon Simple Queue Service (SQS).
  - Simplify your architecture by matching any attribute, or a combination of attributes, for objects in an S3 event. This allows you to filter events by object size, time range, or other event metadata fields before invoking a target Lambda function or other destination. For example, if millions of audio files are uploaded to an S3 bucket, you can filter for specific files and send an event notification to multiple workflows. Through these multiple workflows, the same event can be used to transcribe an audio file, change its media format for streaming, and apply ML to generate a sentiment score.
  - Archive and replay S3 events to reprocess an event in case of an error or if a new application module is added.
- **Use cases**:
  - Easily build and deploy event-driven applications without custom software.
  - Act on new data in S3 faster, make changes to event-driven applications without interruptions, and debug by replaying past events.
  - Use the largest set of destinations on the internet with API destinations.
  
      <img src="images/s3-eventbridge/image1.png" class="inline" width="700" height="250"/>

**Tutorial**
- This tutorial walks you through creating an Amazon S3 Event Notifications with Amazon EventBridge.

 - Step 1: Setup S3 bucket and enable Amazon EventBridge
 
     - Traverse to the <a href="https://console.aws.amazon.com/s3/">Amazon S3 console</a>
     
        <img src="images/s3-eventbridge/image2.png" class="inline" width="700" height="200"/>
       
     - Click on create Create bucket on the right side of the screen
     
        <img src="images/s3-eventbridge/image3.png" class="inline" width="700" height="50"/>
     
     - Provide bucket-name (should be globally unqiue), and leave rest of the option as default. Click Create bucket at the bottom of the page

        <img src="images/s3-eventbridge/image4.png" class="inline" width="700" height="250"/>
            
     - Click on the new bucket created, select Properties and enable Amazon EventBridge under Event notifications section
       
        <img src="images/s3-eventbridge/image6.png" class="inline" width="700" height="275"/>
 
 - Step 2: Configuring Amazon SNS
   
     - Traverse to the <a href="https://console.aws.amazon.com/events/">Amazon SNS console</a>
     
        <img src="images/s3-eventbridge/image7.png" class="inline" width="700" height="175"/>
     
     - Select Topic from left navigation bar, Click Create topic
     
        <img src="images/s3-eventbridge/image8.png" class="inline" width="700" height="200"/>
     
     -  Select Standard as Topic Type, Provide Topic Name, leave rest as default. Click Create topic at the bottom of the page
        
        <img src="images/s3-eventbridge/image9.png" class="inline" width="700" height="225"/>
        
     -  Next let's register subscription under the SNS topic created above, Select Create Subscription

        <img src="images/s3-eventbridge/image17.png" class="inline" width="700" height="150"/>
     
     -  Select Email as an option from Protocol drop-down list and provide your email address

        <img src="images/s3-eventbridge/image18.png" class="inline" width="700" height="225"/>
        
     -  Leave rest as default, scroll down and click Create Subscription

        <img src="images/s3-eventbridge/image19.png" class="inline" width="700" height="150"/>   
     
     -  Post that confirms your subscription via subscription email you would have received on the email-id provided above
        
        <img src="images/s3-eventbridge/image20.png" class="inline" width="700" height="150"/> 
        
        <img src="images/s3-eventbridge/image21.png" class="inline" width="500" height="150"/> 
        
        <img src="images/s3-eventbridge/image22.png" class="inline" width="700" height="150"/> 

- Step 3: Configuring Amazon EventBridge
   
     - Traverse to the <a href="https://console.aws.amazon.com/events/">Amazon EventBridge console</a>
     
        <img src="images/s3-eventbridge/image11.png" class="inline" width="700" height="175"/>
     
     - Click Create rule
     
        <img src="images/s3-eventbridge/image12.png" class="inline" width="700" height="175"/>
     
     - While creating rule we need to provide a couple of details
     
        - Provide Name and description for the rule 
        
          <img src="images/s3-eventbridge/image13.png" class="inline" width="700" height="200"/>
          
        - Under define pattern, select Event pattern, then select Pre-defined pattern by service under Event matching pattern. Now select AWS as Service Provider, Simple Storage Service (S3) as Service name, All Events as Event Type
        
          <img src="images/s3-eventbridge/image14.png" class="inline" width="700" height="500"/>
        
        - Leave Select event bus as default option
        
        - Under Target, select SNS Topic, and select the topic we defined under Step 2 from the topic drop down 
          
          <img src="images/s3-eventbridge/image15.png" class="inline" width="700" height="150"/>
        
        - Click Create at the bottom of the page
        
          <img src="images/s3-eventbridge/image16.png" class="inline" width="700" height="150"/>

- Step 4: Test the setup
