# Submitting data to an Amazon DynamoDB table using the Enhanced Client within a Spring Boot application 

You can develop a fully functioning data submission application by using AWS Services (Amazon DynamoDB and AWS Elastic Beanstalk) and Spring Boot. This application uses the DynamoDB Enhanced Client (**software.amazon.awssdk.enhanced.dynamodb.DynamoDbEnhancedClient**)  to submit data to a DynamoDB table. This application also uses Spring Boot APIs to build a model, views and a controller. 

The DynamoDB Enhanced client lets you map your client-side classes to Amazon DynamoDB tables. To use DynamoDB Enhanced Client, you define the relationship between items in a DynamoDB table and their corresponding object instances in your code. The DynamoDB Enhanced Client class enables you to access your tables; perform various create, read, update, and delete (CRUD) operations; and execute queries.

**Note**: For more information about the DynamoDB Enhanced client, see <X-REF TO Java 2 DEV Guide>. 

The following illustration shows the application that is developed by following this document.

![AWS Blog Application](images/greet1.png)

WHen the **Submit** button is clicked, the data is submitted to a Spring Controller and persisted into a DynamoDB table named **Greeting**. The following illustration shows this table. 

![AWS Blog Application](images/greet2_1.png)

This development document guides you through creating an AWS application that uses Spring Boot. Once the application is developed, this document teaches you how to deploy it to the AWS Elastic Beanstalk.

To follow along with the document, you require the following:

+ An AWS Account.
+ A Java IDE (for this example, IntelliJ is used).
+ Java 1.8 SDK and Maven.

The following illustration shows the project that is created.
![AWS Blog Application](images/greet3.png)

**Cost to Complete**: The AWS Services included in this document are included in the AWS Free Tier.

**Note**: Please be sure to terminate all of the resources created during this document to ensure that you are no longer charged.

This document contains the following sections: 

+ Create an IntelliJ project named **Greetings**
+ Add the Spring POM dependencies to your project	
+ Setup the Java packages in your project
+ Create the Java logic for the main Boot class
+ Create the main controller class
+ Create the Greeting class
+ Create the Service class
+ Create the HTML files
+ Create a JAR file for the **Greetings** application 
+ Setup the DynamoDB table 
+ Deploy the  **Greetings** application to the AWS Elastic Beanstalk


## Create an IntelliJ project named Greetings

**Create a new IntelliJ project named Greetings**

1. From within the IntelliJ IDE, click **File**, **New**, **Project**. 
2. In the **New Project** dialog, select **Maven**. 
3. Click **Next**.
4. In the **GroupId** field, enter **spring-aws**. 
5. In the **ArtifactId** field, enter **Greetings**. 
6. Click **Next**.
7. Click **Finish**. 
