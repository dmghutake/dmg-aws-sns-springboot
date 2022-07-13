# Spring Boot Application to send Notifications from SNS Topic to SQS Queue and Email. 
  * Create Standard SNS Queue for example: brainupgrade-sns-topic.
  * Create Group and add add policies to access SNS programmatically with "AdministrativeFullAccess" and "AmazonEC2FullAccess" and add User to this group with programmatic access.
  * Create Spring boot project from spring Initilizer with web and Lombak dependencey.
  * Once you import project into Eclipse , open pom.xml and add below dependencies.
  ```
    <properties>
  	<spring-cloud-aws-version>2.2.6.RELEASE</spring-cloud-aws-version>
  </properties>

<dependency>
  	    <groupId>org.springframework.cloud</groupId>
  	    <artifactId>spring-cloud-starter-aws</artifactId>
  	    <version>${spring-cloud-aws-version}</version>
  	</dependency>
  	<dependency>
  	    <groupId>org.springframework.cloud</groupId>
  	    <artifactId>spring-cloud-starter-aws-messaging</artifactId>
  	    <version>${spring-cloud-aws-version}</version>
  	</dependency>

  ```
 * Create SNSConfiguration class with Amazon SNS Client Bean with Users access keys.
 * Create SQS Queue to publish the message from SNS Topic.
 * Create Rest Controller and api to subscribe, publish messages. 
 * First Use Rest Client postman to subscribe SQS to SNS Topic.
 * Go to AWS SNS console and check whether SQS subscription is confirmed or not.
 * GO to AWS SQS console and go to SNS subscription. You need to expilcitly select SNS subscription and click on "Subscribe to SNS Topic" button which allows to receive messages to Queue fro SNS topic. Save the changes.
 * Now Use Rest Client postman to publish message SNS Topic. 
 * Test on AWS SQS console whether Messages is present.
 * Create Message Receiver class to receive message from the SQS queue.
 * Test on IDE's console whether Messages is received.
 * Similary write an API to subscribe to email and publish message to topic and check whethere email is received or not. Once you received the email you need to confirm email subscription before sending email messages.
