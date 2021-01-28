# Integrate Cognito with API Gateway
Cognito Authorization:
----------------
Goto Amazon Cognito Service and Click on "Manage User Pools"
![1](https://user-images.githubusercontent.com/63221837/83547236-8a3c5380-a51f-11ea-8f83-7028a2c0f249.png)

Click on "Create a user pool"

![2](https://user-images.githubusercontent.com/63221837/83547239-8b6d8080-a51f-11ea-8068-1b3efe41ae80.png)

Give pool name and click on Review defaults

![3](https://user-images.githubusercontent.com/63221837/83547242-8c061700-a51f-11ea-82cc-861225e6cb5f.png)

Click on Create pool

![4](https://user-images.githubusercontent.com/63221837/83547245-8c061700-a51f-11ea-9790-d07965272e86.png)

Click on Domain name

![5](https://user-images.githubusercontent.com/63221837/83547246-8c9ead80-a51f-11ea-9e19-6d46e119c637.png)

Give Domain prefix and Click on check availability, if it shows This domain is available then click on save changes

![6](https://user-images.githubusercontent.com/63221837/83547250-8d374400-a51f-11ea-9669-1ef8f36da511.png)

Give App client name and click on create app client

![7](https://user-images.githubusercontent.com/63221837/83547251-8d374400-a51f-11ea-8e5b-6c950fa4e65d.png)

Copy App client id and App client secret

![8](https://user-images.githubusercontent.com/63221837/83547252-8dcfda80-a51f-11ea-8780-1166e1d8610a.png)

Click on Resource servers and click on Add a resource server

![9](https://user-images.githubusercontent.com/63221837/83547254-8dcfda80-a51f-11ea-9540-1a96d9e2aa9b.png)

Give Resource server details and click on Save changes

![10](https://user-images.githubusercontent.com/63221837/83547256-8e687100-a51f-11ea-8dd2-b1daf8f0e06e.png)

click on App client settings, select client credentials check box and then allow custom scopes then click on save changes

API Server:
-----------
Goto API Server and create new API
![1](https://user-images.githubusercontent.com/63221837/83548744-e3a58200-a521-11ea-8b07-b2893124abb8.png)

Click on Build with in REST API

![2](https://user-images.githubusercontent.com/63221837/83548732-e0aa9180-a521-11ea-83be-679ba94ea3c8.png)

Give API name and Click on create API

![3](https://user-images.githubusercontent.com/63221837/83548736-e1dbbe80-a521-11ea-92d7-ffa06247ed32.png)

Click on Action and select Create Resource

![4](https://user-images.githubusercontent.com/63221837/83548737-e1dbbe80-a521-11ea-902a-4668992a7d6d.png)

Give Resource name and then click on Create Resource

![5](https://user-images.githubusercontent.com/63221837/83548738-e2745500-a521-11ea-9920-656fdec0b9b0.png)

Click on Action and then click on Create Method
Create GET and POST Methods

![6](https://user-images.githubusercontent.com/63221837/83548740-e30ceb80-a521-11ea-8412-099909f7593c.png)

Click on GET methods, select Mock and then click on Save

![7](https://user-images.githubusercontent.com/63221837/83548742-e30ceb80-a521-11ea-8a12-105c1504e315.png)

Click on Integration Responce

![8](https://user-images.githubusercontent.com/63221837/83548743-e3a58200-a521-11ea-8cae-f5fbb89fcf23.png)

Give above details and then click on save

Deploy API:
------
![1](https://user-images.githubusercontent.com/63221837/83550056-e1442780-a523-11ea-840e-73001e8e4f83.png)

Click on Action and select Deploy API

![2](https://user-images.githubusercontent.com/63221837/83550060-e2755480-a523-11ea-8e6f-6d2ac8d729b1.png)

Give details as above and click on Deploy

![3](https://user-images.githubusercontent.com/63221837/83550062-e2755480-a523-11ea-8110-e1078a379679.png)

Copy API key and give in POSTMAN APP and check output

![4](https://user-images.githubusercontent.com/63221837/83550065-e30deb00-a523-11ea-8403-3b3a3514e300.png)

Open POSTMAN App and select GET method and give URL which we get in API gateway deployment
Click on Send

Now we need to Cognito Authentication for URL in API gateway
--------------------------
![5](https://user-images.githubusercontent.com/63221837/83551529-13ef1f80-a526-11ea-8147-44103072ed02.png)

Click Authorizers and click on create new Authorizers

![6](https://user-images.githubusercontent.com/63221837/83551533-1487b600-a526-11ea-8b5c-5f5f64d908f7.png)

Give details and click on create

![7](https://user-images.githubusercontent.com/63221837/83551535-15204c80-a526-11ea-9821-068d2ec6e327.png)

Goto Resources in API gateway and select GET method and click on Method Request

![8](https://user-images.githubusercontent.com/63221837/83551538-15b8e300-a526-11ea-81f7-282ed2e71e41.png)

Add Autheraization for API methods as show in above
Redeploy our API gateway resource

![9](https://user-images.githubusercontent.com/63221837/83551540-15b8e300-a526-11ea-9427-1ba3fc588542.png)

Goto POSTMAN Method it won't show output as we expected now, it require some authentication

![10](https://user-images.githubusercontent.com/63221837/83551542-16517980-a526-11ea-8171-5c5800eea9c9.png)

With in POSTMAN app click on Autheraization and select OAuth2.0 and then click on Generate Access Token

![1](https://user-images.githubusercontent.com/63221837/83553275-9a0c6580-a528-11ea-87df-5c6f2ff53529.png)

Grab Domain name, ClientID, Client Secret and scope from Cognito and give here and then click on Request Token

![2](https://user-images.githubusercontent.com/63221837/83553279-9aa4fc00-a528-11ea-9937-12b4351241d6.png)

Copy Access Token

![3](https://user-images.githubusercontent.com/63221837/83553280-9b3d9280-a528-11ea-8aef-7e97e61a398d.png)

Open new tab and select Headers, keep key and values as shown above and click on send. we can see output now
Finally we are getting output with cognito authoraization
