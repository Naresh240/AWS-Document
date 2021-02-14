# Classic Load Balancer

# pre-Requisites
    Install httpd on two servers with different content of index.html
# server-1
  ![image](https://user-images.githubusercontent.com/58024415/107868307-69e3d780-6ea9-11eb-8869-7509527e6a5b.png)
# server-2
  ![image](https://user-images.githubusercontent.com/58024415/107868412-23db4380-6eaa-11eb-8f9d-1d56fcf62eb6.png)
# Create Classic load balancer
  ![image](https://user-images.githubusercontent.com/58024415/107868427-4cfbd400-6eaa-11eb-9162-41b415535291.png)
  
  Click on Load Balancer
  
  ![image](https://user-images.githubusercontent.com/58024415/107868455-82082680-6eaa-11eb-9985-1b5cce1b875f.png)

  Click on Create Load Balancer
  
  ![image](https://user-images.githubusercontent.com/58024415/107868472-9fd58b80-6eaa-11eb-891d-53412f3d221e.png)

  Click on Create
  
  ![image](https://user-images.githubusercontent.com/58024415/107868493-baa80000-6eaa-11eb-8021-c29e7454cc88.png)

  Click on Next: Assign Security Group
  
  ![image](https://user-images.githubusercontent.com/58024415/107868528-f642ca00-6eaa-11eb-9911-203f3a1a9b66.png)

  Click on "Next: Configure Security Settings"
  Click on "Next: Configure Health Check"
  
  ![image](https://user-images.githubusercontent.com/58024415/107868548-330ec100-6eab-11eb-9280-4c675d5d11ed.png)

  Click on "Next: Add Tags"
  
  ![image](https://user-images.githubusercontent.com/58024415/107868558-4752be00-6eab-11eb-8d7d-ea4b5733a6ac.png)

  Click on "Review and Create"
  Click on "Create"
  
  ![image](https://user-images.githubusercontent.com/58024415/107868586-808b2e00-6eab-11eb-8175-10148a67f9a3.png)

  Status of both servers showing OutOfService, need to wait until both the servers come to InService.
