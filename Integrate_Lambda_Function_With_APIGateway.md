# Lambda Function - Node.js

Goto AWS Management Console and search Lambda service 
![1](https://user-images.githubusercontent.com/63221837/83593478-7bcf5580-a57a-11ea-9948-21df825f22f0.png)

Click on Create function

![2](https://user-images.githubusercontent.com/63221837/83593481-7d008280-a57a-11ea-95f9-c6ee88c98515.png)

Give Details as shown above and Click on create function

![3](https://user-images.githubusercontent.com/63221837/83593484-7d991900-a57a-11ea-80a1-39dfe99bce33.png)

Goto Function Code and paste below code and save the function

    exports.handler = (event, context, callback) => {
        let min = 0;
        let max = 100;
        let rand = Math.floor(Math.random()*max)+min;
        callback(null, rand);
    };

Click Test button and just accept the popup for test config. Then, we get the number generated and the logs:
![4](https://user-images.githubusercontent.com/63221837/83593486-7d991900-a57a-11ea-97f1-8d8bc4903047.png)

API Gateway - adding trigger:
--------
Goto API Server and create new API
![1](https://user-images.githubusercontent.com/63221837/83548744-e3a58200-a521-11ea-8b07-b2893124abb8.png)

Click on Build with in REST API

![1](https://user-images.githubusercontent.com/63221837/83594326-95719c80-a57c-11ea-8f6a-389043ede85a.png)

Give API name and Click on create API

![2](https://user-images.githubusercontent.com/63221837/83594328-96a2c980-a57c-11ea-9efa-a2ed7aae1e19.png)

Now we'll create a new resource and method:

![3](https://user-images.githubusercontent.com/63221837/83594330-96a2c980-a57c-11ea-9255-9ddb19673ea5.png)

create a GET method:

![4](https://user-images.githubusercontent.com/63221837/83594331-973b6000-a57c-11ea-9425-647532f3a661.png)

Integrate Lambda Function with API Gateway as show above

![5](https://user-images.githubusercontent.com/63221837/83594333-973b6000-a57c-11ea-86d4-ef821e71c4e0.png)

Now we need to deploy our API, for this we need to select Action and then click on Deploy API

![6](https://user-images.githubusercontent.com/63221837/83594336-97d3f680-a57c-11ea-88db-52ec276dbf1b.png)

Create name for New Stage of deployment

![7](https://user-images.githubusercontent.com/63221837/83594337-986c8d00-a57c-11ea-914e-344ebafd6968.png)

Here we get some Deployment URL. Copy this URL and check in POSTMAN app with our API: /randomnumber

![8](https://user-images.githubusercontent.com/63221837/83594338-99052380-a57c-11ea-8002-bbdd89285b29.png)

Open POSTMAN APP and select method as GET and Give URL with out API"

![9](https://user-images.githubusercontent.com/63221837/83594339-99052380-a57c-11ea-9467-76198ce20d68.png)
