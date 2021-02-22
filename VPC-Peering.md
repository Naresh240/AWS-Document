# VPC Peering
  VPC peering is nothing but establishing bridge between two VPC's in different Availability zones or different Regions
# We need to create two vpc's with different availability zones
  Now going to create vpc's in a simplest way
# Create VPC10:
![image](https://user-images.githubusercontent.com/58024415/95078768-4b1f4880-0733-11eb-99f8-44aa14e5fe3e.png)

Click on VPC Dashboard and then Click on Launch VPC Wizard

![image](https://user-images.githubusercontent.com/58024415/95078868-71dd7f00-0733-11eb-85f9-9faf8f8d1d14.png)

Click on Select

![image](https://user-images.githubusercontent.com/58024415/95078936-89b50300-0733-11eb-93a6-e6e99a2fe3a4.png)

Click on Create VPC

# Create VPC11:
![image](https://user-images.githubusercontent.com/58024415/95079070-c08b1900-0733-11eb-82d3-a1b138f74bc8.png)

Click on Create VPC

# Create Instance with vpc10
![image](https://user-images.githubusercontent.com/58024415/95079245-f7f9c580-0733-11eb-8972-a5e2eff23104.png)

Connect to server which is inside vpc10

![image](https://user-images.githubusercontent.com/58024415/95079599-7bb3b200-0734-11eb-855d-9d0cb246ed0c.png)

# Create Instance with vpc11
![image](https://user-images.githubusercontent.com/58024415/95079727-a7369c80-0734-11eb-8b60-0f8d9d61c204.png)

Connect to server which is inside vpc11

![image](https://user-images.githubusercontent.com/58024415/95079892-e1a03980-0734-11eb-966b-bdf44162fdef.png)

Try to ping vpc11 server with vpc10 server

![image](https://user-images.githubusercontent.com/58024415/95079962-fc72ae00-0734-11eb-822b-a2e4008073fd.png)

It won't give any response, so need to create peering between two servers

# Create peering between vpc10 and vpc11

![image](https://user-images.githubusercontent.com/58024415/95080109-35128780-0735-11eb-915d-7fb68a945c7d.png)

Click on Create Peering Connection

![image](https://user-images.githubusercontent.com/58024415/95080253-73a84200-0735-11eb-94e5-0195c3a83776.png)
![image](https://user-images.githubusercontent.com/58024415/95080390-ae11df00-0735-11eb-9008-99c6158a08d3.png)

Click on Create peering connection

![image](https://user-images.githubusercontent.com/58024415/95080475-c84bbd00-0735-11eb-942d-65709d38e364.png)

Peerig connection established

![image](https://user-images.githubusercontent.com/58024415/95080845-5162f400-0736-11eb-8cd7-f69225093f9d.png)

Please accept request then it comes to active state

Now attach peering in both Routing tables as routes

vpc10 routing table:

![image](https://user-images.githubusercontent.com/58024415/95082673-05fe1500-0739-11eb-92fa-e29e19a04789.png)

vpc11 routing table:

![image](https://user-images.githubusercontent.com/58024415/95082600-e666ec80-0738-11eb-900a-40bab7d308bb.png)

Open ICMP in Inbound rules of both security groups

![image](https://user-images.githubusercontent.com/58024415/95082743-24fca700-0739-11eb-96df-14912c647d8b.png)

Now see ping in both the servers

![image](https://user-images.githubusercontent.com/58024415/95082952-773dc800-0739-11eb-8926-83ffb8f4e1ef.png)

&

![image](https://user-images.githubusercontent.com/58024415/95083041-92a8d300-0739-11eb-8620-9243df261dba.png)
