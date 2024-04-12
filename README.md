# Networking-fundamentals
Important concepts about Networking

1) IP address:
   
It is basically a unique address for a device on a nework by which aparticular device on a network can be uniquely identified.
Generaing IP address for each device the standard that is followed is IPV4.(USING IPV4 we can generate huge no. of ip addresses)

########### Understanding the concept of IPV4 ##########

Q) How many unique address can be created using IPV4 standard?

--> Since an IPV4 address is made of 4 bytes = each byte of 8 bit (2^8 = 256 i.e 0-255). 
so each of the 4 places in an IPV4 address can generate 255 combinates. so total combinations possible would be
(255 * 255 * 255 * 255) ---> THIS MANY NO. OF UNIQUE IP ADDRESS can be generated using IPV4 standard.

Note: you wouldnt see an ip address 400.450.600.756(❌)
According to IPV4 standard the no. at anyy of the 4 places should be less than 255 then only it is an valid IP address ex:172.56.23.2(✅)

Important thing to note: we are representing ip address as shown in the ex above but computer understands by converting it into a binary no.
Ex: ![image](https://github.com/userasher/Networking-fundamentals/assets/109350583/1f5bc44b-ba24-4814-9177-e5eb27727184)


############ Concept of subnet #########
Q) What is subnetworking?
A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient. Through subnetting, 
network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination. 
Subnets basically ar epart of bigger netwroks which are broken down.

Q)Advantages of subnetworking?

-->security
privacy
isolation from malicious/other subnets


Q)types of subnets and difference between them?

--> 1)private subnet and public subnet
diff---> private subnet doesn't have access to internet
        public has access


Q) what if for some reason you need to allocate particular no. of addresses in your private to a particular subnet in your network?

---> solution to that is CIDR.
EX: 
![image](https://github.com/userasher/Networking-fundamentals/assets/109350583/18ad86b0-f382-4e5d-9cac-cbe6f2ec00a6)


Lets suppose this(image above) the range of IP addressES provided by your by cloud provider and 
you need to give 256 no. of IP addresses to your subnet 1 and all rest IP addresses 
to your subnet 2
How this will be done ?

---> 1) 1st from the image you can understand that your cloud provider gave you (256* 256) = 65536 ip addresses.

    2) then we can say that 1st bytes will always be static and last 2 bytes will change to get total of 65536 IP addresses

    3) nOW LETS choose 172.16.3.0 as base ip address fro assigning 256 Ip address to subnet 1. 
    for ex: you can any of them with 3rd byte varying from 0-255
    for ex: 172.16.3.0
            172.16.4.0
            172.16.5.0
            172.16.5.0
            172.16.7.0
            172.16.8.0

    4) Now CIDR as concept says for assigning 256 IP address you will 
    asked for CIDR range and you should provide : 
    172.16.3.0/24 (so this is what will be provided in 
    CIDR range) 

    Now lets understand where did this 24 came from

    formula: 
    
    🤌🤌🤌🤌🤌32 - (the no. you will write here is the no. you write after the slash) = 2^(what were you get from subtraction)🤌🤌🤌🤌🤌 
    ( 32 because to represent ip address in binary we need 32 bits 
    and after slash we represent how many bits we will keeping static so that we get 256 IP addresses)

    Explanation of the formula:  
    so we want 256 

    32 - 24 = 8 ====> 2^8 = 256 so we are supposed to write 24 after the slash i.e 172.16.3.0/24

    Another example: lets say you only need to assign 2 ip address
    you choose base ip address as 172.16.3.0

    so for 2 ip addresses you will need 1 as the answer of the subtraction right!!
    because 2^1 = 2
    so 32 - x = 1 i.e x = 31 (so our answer is 172.16.3.0/31) i.e we will provvide 172.16.3.0/31in cidr range when asked 

    Note: lets say we need to calculate no. of IP addresses form give cidr range
    10.0.0.0/8 ===> formula ===> 32 - 8 = 24 ====>no. of IP add. = 2^24










   
