# Managing-user-access-via-AD-DS

Tools > Users and Computers

![image](https://github.com/user-attachments/assets/219d68eb-bd3b-4a44-b8e1-185ab3a09d8a)

Users > New > User

![image](https://github.com/user-attachments/assets/edc4a9c5-7e4a-4c31-ab8c-801b2cfebc75)


![image](https://github.com/user-attachments/assets/d9751f32-710a-44b9-b380-2486ebafc73c)

![image](https://github.com/user-attachments/assets/ef5fcb1b-b8c6-44ee-b1f0-eeda0e545905)

![image](https://github.com/user-attachments/assets/d078f2ef-a6e6-4ba5-adc1-ed0e2592ddfd)

![image](https://github.com/user-attachments/assets/560b4388-6f0a-42fe-a640-11be85c225d1)

Make sure the client is linked to the domain

![image](https://github.com/user-attachments/assets/67fb8ec0-2e01-409c-b737-e5d3b4064bfb)

Pinging the server to make sure the connection was established correctly 
```bash
ping <your server IP address>
```

No packet loss means we're not dropping any packets

![image](https://github.com/user-attachments/assets/3e80fabc-dc97-4c8a-b508-aceb0e3dde83)

Note : If you get 100% packet loss make sure to configure the firewall to allow inbound traffic
![image](https://github.com/user-attachments/assets/ba65f67b-a6c7-41fe-aeca-467e42f25512)

Go to windows firewall with advanced settings :

![image](https://github.com/user-attachments/assets/870aa246-019e-4538-a688-19789261b71f)

Inbound Rules > File and Printer Sharing (Echo Request ICMPv4-In)

![image](https://github.com/user-attachments/assets/0459acfa-52d7-4d37-9a75-7369fab06c80)

Add the server IP address will allow it to ping the client

![image](https://github.com/user-attachments/assets/dd091d71-5e70-4110-96cc-81719a931d38)

Right click > Enable Rule
![image](https://github.com/user-attachments/assets/819329e2-8936-45aa-8bd5-683084d6103d)


Allow remote connection (optional)

```
Win + I > Rename this PC (Advanced) > Remote
```
![image](https://github.com/user-attachments/assets/98fba8c0-ee51-43f5-b246-90c803de9447)


Select local principals and add the server :
![image](https://github.com/user-attachments/assets/41cffb31-5d3b-4406-a797-4a251eda58bb)

or you could add user to remote control users group from your server :

![image](https://github.com/user-attachments/assets/a6379bea-80f4-43ed-b50b-9ce2181ec595)

Tools > Group Policy Management

![image](https://github.com/user-attachments/assets/da52d336-0e2f-4566-acce-930f6672b002)

Creating new Group Policy :

![image](https://github.com/user-attachments/assets/2850bdb7-8b3a-4030-a71c-08efef470035)

![image](https://github.com/user-attachments/assets/acc3b088-7061-40cc-92dd-bfc95545bd57)

We can see it's been added 
![image](https://github.com/user-attachments/assets/abfdfabb-bcaa-45d8-9d76-cb421a37d7c6)

Let's push some Group Policies shall we ?

![image](https://github.com/user-attachments/assets/83a89f40-7eab-4863-8a97-007af5b9b31e)

![image](https://github.com/user-attachments/assets/64a1dd1b-f863-4db1-a313-5f43341cd6b4)

![image](https://github.com/user-attachments/assets/ac91e704-c94c-474b-a421-f6e3055e5320)

Edit the policy

![image](https://github.com/user-attachments/assets/29d3e3f6-6e13-4aea-a630-75868dd4673a)

Configure the firewall 

![image](https://github.com/user-attachments/assets/eea85de7-fb80-4bb6-9968-330f5bd9236b)

Click on properties > Select On

![image](https://github.com/user-attachments/assets/945f7bfb-75b3-4a0e-a355-97dcac5fa883)

Configure the Allow / Block settings for the domain profile then click OK

![image](https://github.com/user-attachments/assets/58f96e12-05f0-45a2-ab27-2fa72eb1da38)

Allowing remote desktop connection
Policies > Windows Settings > User Rights Assignment > Allow log on through Remote Desktop Services

![image](https://github.com/user-attachments/assets/e0098cfd-407d-498c-8041-af6450203334)

![image](https://github.com/user-attachments/assets/e06c4969-50fc-4146-b0bb-a9a8ed8601a4)

Click check names then OK

![image](https://github.com/user-attachments/assets/f5524dc4-19da-45dd-9fea-30b6b3b70eb9)

I also added Domain Users to showcase that you're not limited to adding one group

![image](https://github.com/user-attachments/assets/60948d7c-0c6e-461e-ba9b-6f038b0e2bb7)

Policy settings are now defined

![image](https://github.com/user-attachments/assets/6cdf56a2-4060-4ce5-9c2e-37484bc7adda)

Update Policy 

![image](https://github.com/user-attachments/assets/6bd3d7ed-0dd3-44a4-92f7-ccb122a945ac)

#### Making the web app accessible to the other clients aka Updating Web App Binding



