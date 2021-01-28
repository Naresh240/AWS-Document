# Integrate Cognito Service With APIGateway

Goto Amazon Cognito Service and Click on "Manage User Pools"
![1](https://user-images.githubusercontent.com/63221837/83547236-8a3c5380-a51f-11ea-8f83-7028a2c0f249.png)

Click on "Create a user pool"
![1](https://user-images.githubusercontent.com/63221837/83595598-20a06180-a580-11ea-8f9d-f22fd4ff48b5.png)
Give pool name and click on Review defaults

![2](https://user-images.githubusercontent.com/63221837/83595602-226a2500-a580-11ea-973d-c04f49761576.png)

Give App Client Name and then click on Create App client name
Now Goto click on Review and then Click on "Create User Pool"

Now we need to create a Domain Name, for this we need to click on domain name

![3](https://user-images.githubusercontent.com/63221837/83595604-226a2500-a580-11ea-9db4-47f5d04a5d29.png)

Give Domain prefix and check availability. If it is available click on save changes

Now we need to add Resource Server for our App client. Here we can create scopes
![4](https://user-images.githubusercontent.com/63221837/83595605-2302bb80-a580-11ea-99f6-1f298d52d200.png)

Click on Resource servers and give name for Resource server, Identifier and scopes. Then click on save changes

![5](https://user-images.githubusercontent.com/63221837/83595607-239b5200-a580-11ea-9815-282a62b19d7e.png)

Attach this Scope to our App Client. Click on App Client settings

![6](https://user-images.githubusercontent.com/63221837/83595608-2433e880-a580-11ea-8d6f-71fe0a8133a4.png)

Select Client Credentials and then select Allow custom scopes then save

Now we are going to integrate Cognito with API Gateway:
---------------
Open API Gateway and Create Authorizer

![1](https://user-images.githubusercontent.com/63221837/83596729-05832100-a583-11ea-94ca-35f3095b4b0b.png)

Give data as show in above figure and click on create 

![2](https://user-images.githubusercontent.com/63221837/83596730-06b44e00-a583-11ea-85ae-03a59fced279.png)

Goto GET Method and Click on Method to attach authentication to our API




Give atherization and Oath scope and then save
Once again Deploy our API.
Goto POSTMAN APP and check we can get output or not

![3](https://user-images.githubusercontent.com/63221837/83596731-074ce480-a583-11ea-8d48-e0cfc7f08f62.png)

See here we get some message like "Unauthorized"

![7](https://user-images.githubusercontent.com/63221837/83596900-7a565b00-a583-11ea-8d48-f0c3ff14b929.png)

If we want to see proper output we need to generate some token with App Client id and App client secret

![4](https://user-images.githubusercontent.com/63221837/83596732-074ce480-a583-11ea-9687-9152c7c7d94b.png)

Give details of domain name, App Client id, App client secret and scope then click on Generate token
we need to give "/oauth2/token" alone with domain name
Now Give Token with Header and check whether we are getting expected output or not

![6](https://user-images.githubusercontent.com/63221837/83596736-087e1180-a583-11ea-98c1-543b1f3420ff.png)







