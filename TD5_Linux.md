TD4*

# Exercise 1: SSH
1. Create an account on a cloud computing platform (AWS, Azure, Google
Cloud, IBM Cloud)
— You must enter your credit card number, I have no affiliation
— It is free. Delete the account in few month to prevent any fee
```
I am on AWS
```
2. Create a server instance on the website of your cloud platform (ec2 for
AWS, Standard B1s for Azure)
```
Done
```
3. Connect to the distant server via your terminal
— Do chmod 400 your private key file. The connection won’t work otherwise
— Use an SSH instruction to connect to your remote instance
— Exit to return to your local machine
```
chmod 400 Key_Projet_Linux.pem
ec2-16-170-219-132.eu-north-1.compute.amazonaws.com
ssh -i "Key_Projet_Linux.pem" ec2-user@ec2-16-170-219-132.eu-north-1.compute.amazonaws.com
exit
```
4. Create a script named connect.sh to automatically connect to the remote
instance
```
vim connect.sh
```
5. Run the script to check it is working properly. Then exit to return to
your local machine.
```
source connect.sh
exit
```



# Exercise 2: SCP
1. On your local machine create a file named test_to_remote_instance.txt
```
>test_to_remote_instance.txt
```
2. Connect to your remote instance and create a file named test_from_remote_instance.txt.
Then exit
```
source connect.sh
>test_to_remote_instance.txt
exit
```
3. Use the scp command to :
— Send your file test_to_remote_instance.txt to the home folder of your
remote instance
— Get the file test_from_remote_instance.txt to your current local directory
```
scp  ec2-user@ip... :/ ~/test_to_remote_instance.txt fraart@... :/ ~
```
