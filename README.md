
  ![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/872da474-62a6-41bc-9d80-1642bcc98f4e)


<h1>Network File Shares and Permissions</h1>
In this tutorial I will demonstrate how to  share out resources over the network. We can create folders and allow certain users to have access to them. 






<h2>Deployment and Configuration Steps</h2>
  
First were going to create folders in the domain controller's C drive. Create the following folders: “read-access”, “write-access”, “no-access”, and “accounting”. For the "no access" file, we are going to add only Domain admins to the list of users that we want to have access to this file. The normal user on Client-1 will not be added to this list therefore it will not be able to gain access to this file. 

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/8ab1900f-89aa-40ac-a84b-30fe15fa36da)

Attempt to access the "no access" file as a normal user on Client-1. As you will find, you are unable to do so because that user wasn't granted access to that file in the file sharing in properties. 


![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/c418edf5-863b-4220-a6c6-3f1bbc58ea6f)

With Security group, we can set file permissions easily. When selecting a security group in file share, all the users that are members of that security group will have access to that file. Anyone who is not part of that group will not be able to gain access to that file. Create an “ACCOUNTANTS” Security Group and assign permissions then we will test access.

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/cc22e50c-451a-4a7a-8a3b-ef39c5b4085b)

On the “accounting” folder you created earlier, set the following permissions:
Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”


![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/5264aafc-33f9-421c-b3fe-f24d49f923d8)

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/9a4f4aa1-2d61-4cd5-aad4-d7e892cc60fc)

Now we can add the user on client-1 to the "ACCOUNTANTS" security group so they can access the Accountant file. 

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/9fa0cc7d-cb59-4edb-bc34-5a2fbf15aa6c)

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/47ea3665-c8b6-44f0-b90c-d0f8e06ac1f7)


Once the user is added to the serurity group, you must log out and log back in in order for it to take effect. Failer to log out and back in will result to access denial of the particular folder you are trying to access.  

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/cb4cbcd1-c188-4eed-91ea-e44581e11df0)

Now the file has been accessed by the user.

![image](https://github.com/AntIT-1/network-files-and-permissions/assets/141161539/0e8d2459-fd9b-4f7e-bde7-18f059d3f73a)







