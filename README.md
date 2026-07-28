# VIRTUAL PRIVATE CLOUD (VPC) CREATION AND LAUNCHING AN AMAZON EC2 INSTANCE IN AWS

## Aim

To create and configure an Amazon Virtual Private Cloud (VPC) with public and private subnets, configure route tables and a security group, launch an Amazon EC2 instance inside the VPC, and verify that the hosted web application is accessible through the internet.

---

## Algorithm / Steps

1. Log in to the AWS Management Console.
2. Open the Amazon VPC service.
3. Create a new VPC named **lab-vpc** with the IPv4 CIDR block **10.0.0.0/16**.
4. Enable DNS Resolution and DNS Hostnames for the VPC.
5. Create a public subnet named **lab-subnet-public1-us-east-1a**.
6. Create a private subnet named **lab-subnet-private1-us-east-1a**.
7. Create an Internet Gateway and attach it to the VPC.
8. Create a NAT Gateway inside the public subnet.
9. Create a public route table and associate it with the public subnet.
10. Create a private route table and associate it with the private subnet.
11. Create an additional public subnet named **lab-subnet-public2**.
12. Create an additional private subnet named **lab-subnet-private2**.
13. Associate the new public subnet with the public route table.
14. Associate the new private subnet with the private route table.
15. Create a security group named **lab-sg**.
16. Add inbound rules to allow SSH (Port 22) and HTTP (Port 80).
17. Launch an Amazon EC2 instance using the Amazon Linux 2023 AMI.
18. Select the **t2.micro** instance type.
19. Attach the **lab-sg** security group to the EC2 instance.
20. Enable Auto Assign Public IP.
21. Launch the EC2 instance.
22. Wait until the instance reaches the **Running** state.
23. Access the EC2 instance using its public IPv4 address.
24. Verify that the hosted web page is displayed successfully.

---

## Program
## Name : Naveen Kumar S
## Reg No : 212224040214

### 1. Create a VPC

- Name : **lab-vpc**
- IPv4 CIDR : **10.0.0.0/16**

---

### 2. Create Public Subnet

- Name : **lab-subnet-public1-us-east-1a**
- IPv4 CIDR : **10.0.0.0/24**

---

### 3. Create Private Subnet

- Name : **lab-subnet-private1-us-east-1a**
- IPv4 CIDR : **10.0.1.0/24**

---

### 4. Create Public Subnet 2

- Name : **lab-subnet-public2**
- IPv4 CIDR : **10.0.2.0/24**

---

### 5. Create Private Subnet 2

- Name : **lab-subnet-private2**
- IPv4 CIDR : **10.0.3.0/24**

---

### 6. Create Security Group

Security Group Name

```text
lab-sg
```

Inbound Rules

```text
SSH (TCP - Port 22)
HTTP (TCP - Port 80)
```

---

### 7. Launch Amazon EC2 Instance

Configuration

```text
AMI           : Amazon Linux 2023
Instance Type : t2.micro
VPC           : lab-vpc
Subnet        : lab-subnet-public2
Security Group: lab-sg
Public IP     : Enabled
```

---

### 8. Verify the Web Server

Open the Public IPv4 Address in a web browser.

Expected Output

```text
AWS Web Server Page

Instance ID
Availability Zone
Current CPU Load
```

---

## Outputs

### Output 1: Amazon VPC Created Successfully

The AWS VPC dashboard displays the newly created **lab-vpc** with the IPv4 CIDR block **10.0.0.0/16**. The VPC is in the **Available** state with DNS Resolution and DNS Hostnames enabled.

<img width="1600" height="765" alt="WhatsApp Image 2026-07-29 at 01 43 52" src="https://github.com/user-attachments/assets/8afc9fe6-f05e-4e61-b621-00c574367e32" />


---

### Output 2: Public Subnet Created Successfully

The AWS Subnets page confirms that **lab-subnet-public2** has been created successfully with the IPv4 CIDR block **10.0.2.0/24** and is associated with **lab-vpc**.

<img width="1600" height="854" alt="WhatsApp Image 2026-07-29 at 01 43 52 (1)" src="https://github.com/user-attachments/assets/b545d35d-a634-4ef1-a1df-4f79dcdb1a94" />


---

### Output 3: Private Subnet Created Successfully

The AWS Subnets page confirms that **lab-subnet-private2** has been created successfully with the IPv4 CIDR block **10.0.3.0/24**.

<img width="1600" height="857" alt="WhatsApp Image 2026-07-29 at 01 43 52 (2)" src="https://github.com/user-attachments/assets/51e84fc9-a655-4ed6-abc3-786a812a526e" />


---

### Output 4: All Subnets Created Successfully

The Subnets page displays all four configured subnets:

- lab-subnet-public1-us-east-1a
- lab-subnet-private1-us-east-1a
- lab-subnet-public2
- lab-subnet-private2

All subnets are shown in the **Available** state.

<img width="1600" height="773" alt="WhatsApp Image 2026-07-29 at 01 43 53" src="https://github.com/user-attachments/assets/143fdb8b-4f3c-4ba9-8d7a-3942b562d9ae" />


---

### Output 5: VPC Resource Map Verified

The VPC Resource Map displays the complete cloud network architecture including the VPC, public and private subnets, and route tables.

<img width="1600" height="761" alt="WhatsApp Image 2026-07-29 at 01 43 53 (1)" src="https://github.com/user-attachments/assets/d0c97ae0-be63-4575-ace7-cca0643cf9ea" />


---

### Output 6: Security Group Created Successfully

The AWS Security Group **lab-sg** was successfully created with inbound rules allowing **SSH (Port 22)** and **HTTP (Port 80)** traffic.

<img width="1600" height="771" alt="WhatsApp Image 2026-07-29 at 01 43 54" src="https://github.com/user-attachments/assets/f094c9f9-d24b-49da-999d-a541cbfdc7fc" />


---

### Output 7: Amazon EC2 Instance Launched Successfully

The EC2 console displays the successful launch of the Amazon Linux 2023 instance and confirms that the launch process has been initiated successfully.

<img width="1600" height="858" alt="WhatsApp Image 2026-07-29 at 01 43 54 (1)" src="https://github.com/user-attachments/assets/bdbb1a73-d5cf-40ea-9deb-caac8b8bb883" />


---

### Output 8: EC2 Web Server Verified Successfully

The EC2 hosted web application is successfully accessed through the Public IPv4 address. The page displays the Instance ID, Availability Zone, and Current CPU Load, confirming that the web server is functioning correctly.

<img width="955" height="900" alt="WhatsApp Image 2026-07-29 at 01 47 08" src="https://github.com/user-attachments/assets/d87df245-6a45-45d5-ab0f-9e5fc8a7552b" />


---

## Result

Thus, an Amazon Virtual Private Cloud (VPC) was successfully created with public and private subnets, route tables, an Internet Gateway, a NAT Gateway, and a security group. An Amazon EC2 instance was successfully launched within the VPC using the Amazon Linux 2023 AMI. The hosted web application was successfully accessed through the Public IPv4 address, demonstrating successful deployment and configuration of the AWS cloud infrastructure.
