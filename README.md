# AWS Account Creation and EC2 Instance Setup

## Lab Mission
Create an AWS account and EC2 instance with basic configuration, and connect to the new instance via RDP.


## Resources
- **Environment & Tools**
  - Web Browser
  - Remote Desktop (RDP)
- **Miscellaneous**
  - Payment method (credit card, billing address, email address)
  - Working phone number (for text authentication and confirmation)

## External Lab Links
- **AWS Documentation:**
  - [AWS Documentation](https://docs.aws.amazon.com/)
- **AWS Free Tier Limits Documentation:**
  - [Free Tier Limits](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-limits.html)

---

## Lab Task 1: Create an AWS Account
Create an account in AWS to use its services. Specify real data for the account. This will require a financial relationship with Amazon (AWS) since you will be providing a credit card to cover the cost of the infrastructure on a pay-as-you-go basis. The intent is to utilize the 750 free hours that Amazon provides to learn their platform. More information is available from AWS Free Tier.


1. Go to [AWS](https://aws.amazon.com).
2. Click **Sign in to the Console** (top-right corner). This will open another page where you will **Create a New AWS Account**.
3. Fill in the required fields for the account root user email address and AWS account name.
4. You will be sent a verification code for the AWS account that expires after 10 minutes.
5. Enter the root user password.
6. In **Contact Information**, select the account type **Personal**, fill in the required information, and click the checkbox to agree to the AWS Customer Agreement. Click **Create Account and Continue** once you have entered the required information.
7. Fill in the required payment information and click **Verify and Add** to continue.
8. Add your phone number and complete the security form to receive a verification code via text message. Click **Send SMS** to continue.
9. Enter the verification code.
10. Select the **Basic Plan**.
11. On the welcome page that appears, you can sign in to your account via the **Go to the AWS Management Console**.

---

## Lab Task 2: Create a New EC2 Instance
In this task, you will create and configure an EC2 instance to contain the virtual Windows Server 2016 base operating system.

1. Sign in to the AWS console using the email address and password you used to create the account in Task 1. If prompted for Root user or IAM user, choose **Root user**.
2. Once logged in, use the new console and select **Switch to the new Console Home**.
3. In the console at the top, click on **Services** to access a dropdown menu and type **EC2** in the search bar. Click on **EC2** to get to the EC2 Dashboard.
4. In the EC2 dashboard, click the **Launch Instance** dropdown menu and select **Launch Instance**.
5. In the search, type *Windows 2016*, then select the *Microsoft Windows Server 2016 Base Amazon Machine Image (AMI)*. Confirm that it is labeled **Free tier eligible** and click **Select**.

   > **Note:** You may need to confirm the change.

6. Go to **Key pair** and select **Create new key pair**. Input the name for your `.pem` or `.ppk` file, then click **Create key pair**.
7. Make sure to save and store the Key pair file. You will use it later for the RDP connection to the server.
8. Check the **Network settings** and change the RDP traffic to your IP address.
9. Initiate **Launch instance** which is found on the right side under **Summary**. The instance will begin, and you should receive a success message with your instance ID. Near the bottom of the screen, click on **View all instances**.

---

## Lab Task 3: Connect to the Instance via RDP
In this task, you will establish the remote connection to the instance using the downloaded RDP executable and the key.

1. Right-click the instance and select **Connect**.
2. In the **Connect to Your Instance** window, click **Download Remote Desktop File** and save the file to your computer. Remember where you saved it. After you download the file, click **Get Password**.
3. In the **Connect to your instance > Get Password** window, for **Key Pair Path**, click **Browse** and navigate to the key pair file that you downloaded. This file was created in Lab Task 2, Step 6 (file extension `.pem`). Then click **Decrypt Password**.
4. After decrypting the password, the administrator account in the Windows 2016 AWS host that you created will now be visible. Copy the password to a text file on your computer.

   > **Note:** Your public DNS name will be different than the one listed below, as it is unique for each AWS instance.

5. To launch a remote desktop connection to your AWS instance (while the instance is running), double-click the RDP file you downloaded in Step 2. You will be prompted to enter the credentials for the administrator account using the password from Step 4.

---

## Notes:
- When you first log into your AWS Windows instance, the setup process will take a few minutes to complete. You may experience a black screen for up to 5 minutes.
- Even though you created a Free Tier server, you may still be charged for the instance after 750 hours of runtime. For more details about AWS tier limits, visit the [AWS Free Tier Limits](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/free-tier-limits.html).

---

## Conclusion
Congratulations! You are now logged into your Windows 2016 EC2 instance in AWS!

> **Important:** Turn off the instance by going back to the instance menu in Task 2, Step 9; right-clicking the instance; and selecting **Instance State** -> **Stop**.
