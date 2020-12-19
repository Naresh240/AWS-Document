# System Manager

# Create Role with below policies:
	  -	AWSConfigUserAccess
	  -	AmazonSSMFullAccess
# Attach SSM role with EC2 Instance
# Do AWS configure in local for providing region
    aws configure
  ![image](https://user-images.githubusercontent.com/58024415/102684670-c8ba0700-4200-11eb-8c15-2151c6c13c5a.png)
# Create put parameters for mail address in ssm 
    aws ssm put-parameter --name "FROM_MAIL" --type "String" --value "naresh240.qis@gmail.com"
    aws ssm put-parameter --name "TO_MAIL" --type "String" --value "naresh240.qis@gmail.com"  
  ![image](https://user-images.githubusercontent.com/58024415/102684676-dd969a80-4200-11eb-8b24-62c9658cc15f.png)
# Check wether parameters created or not
  ![image](https://user-images.githubusercontent.com/58024415/102684693-fb63ff80-4200-11eb-8202-17cfebd45f23.png)
