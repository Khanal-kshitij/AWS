# Creating an Application load balancer in AWS
1.create vpc '''10.0.0.0/16'''

![Screenshot (110)](https://github.com/user-attachments/assets/30f2dcdf-9e56-4015-be5d-11dd6ad19b56)


2.THEN CREATE INTERNET GATEWAY AND CONNECT VPC TO IT AND THEN CREATE VGW AND CONNECT(ATTACH) VPC TO IT. NOW GO TO ROUTE TABLES AND CREATE 2 ROUTE 
  TABLE - R1-IGW , R2-VGW AND EDIT ROUTES WITH 0.0.0.0/0 AND 192.168.0.0/16 RESPECTIVELY AND TARGET IGW AND VGW RESPECTIVELY.
  
3.Now create 2 instances of same type with select VPC which you created and using putty download apache-2 on both and edit like test-1 and test-2 respectively for better understanding.

4.Now to create LOAD BALANCER (WE NAMED server-computer HERE ) OF APPLICTION TYPE , WE NEED TO CREATE TARGET GROUP AND ATTACH BOTH EC2 INSTANCES WE CREATED AND EDIT HEALTH CHECK-UPS 

5.AND NOW SELECT THIS TARGET (WE NAMED AS T-1 HERE) AND CREATE LOAD BALANCER , NOW COPY YOUR LOAD BALANCER'S DNS NAME AND PASTE IT IN OTHER TAB AND RELOAD TWICE TO SEE ITS WORKING.
### NOW ON ANY 1 INSTANCE WRITE FOLLOWING COMMANDS IN PUTTY-
```
seq 999999999999999999999 > /dev/null &
```
**for making Artificial load
```
htop
```
**for monitoring
