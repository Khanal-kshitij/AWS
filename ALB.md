# Creating an Application load balancer in AWS
1.create vpc '''10.0.0.0/16'''

![Screenshot (110)](https://github.com/user-attachments/assets/30f2dcdf-9e56-4015-be5d-11dd6ad19b56)

2.create internet gateway and attach it to vpc

![Screenshot (111)](https://github.com/user-attachments/assets/08590a29-0c53-43ba-9832-ee736e5ceef1)

3.create 4 subnets,2 public,2 pvt


![Screenshot (114)](https://github.com/user-attachments/assets/7e3780de-afec-4345-a910-447342310cb0)

4.create 2 route table and associate it with the 4 subnets provide internet access to route table.


![Screenshot (115)](https://github.com/user-attachments/assets/a3dcbfab-eff7-4791-8259-72cbd3920c99)

5.Now create 2 ec2 instances of same type with select VPC which you created and using putty download apache-2 on both and add web server on both of them.


![Screenshot (116)](https://github.com/user-attachments/assets/6c1d34bf-9c3f-4c48-b93b-0420eb57f135)


6.Now to create Application LOAD BALANCER, WE NEED TO CREATE TARGET GROUP AND ATTACH BOTH EC2 INSTANCES WE CREATED AND EDIT HEALTH CHECK-UPS

7.Create or select a security group for the ALB that allows inbound traffic on the necessary ports (e.g., 80 for HTTP and 443 for HTTPS).

8.Configure Listeners and Target Groups.

![Screenshot (118)](https://github.com/user-attachments/assets/3a61cfb8-a81d-4443-b2fc-72d986ea0e4a)


![Screenshot (119)](https://github.com/user-attachments/assets/aeed70dd-29a4-4643-8efd-bd8150f494a1)


![Screenshot (120)](https://github.com/user-attachments/assets/a3507804-d488-44f9-bbf3-c6ee1adf72d6)


![Screenshot (121)](https://github.com/user-attachments/assets/436a976d-bda9-4f8d-b3be-e0f2bfb6e049)


### NOW ON ANY 1 INSTANCE WRITE FOLLOWING COMMANDS IN PUTTY-
```
seq 999999999999999999999 > /dev/null &
```
**for making Artificial load
```
htop
```
**for monitoring
