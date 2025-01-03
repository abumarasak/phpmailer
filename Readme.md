# **Sending Emails with PHPMailer and .env Configuration**

This guide explains how to set up a simple PHP application to send emails using PHPMailer and store sensitive credentials in a `.env` file. The setup includes an HTML form to collect recipient email, subject, and message, which are sent via email using Outlook SMTP.

---

## **Requirements**

1. **Requirement 1: PHP installed on your system (preferably with XAMPP or WAMP).**
2. **Requirement 2: Composer installed on your system.**
3. **Requirement 3: PHPMailer and `vlucas/phpdotenv` packages.**

---

## **Setup Instructions**

### **Step 1: Clone or Download the Project**

Ensure you have the project files, including:

- `index.html` (HTML form for sending email)
- `send_email.php` (PHP script to process the form and send the email)

### **Step 2: Install Dependencies**

1. Open a terminal or command prompt.
2. Navigate to the project directory.  
   cd path/to/your/project
3. Run the following command to install PHPMailer and Dotenv:  
   composer require phpmailer/phpmailer vlucas/phpdotenv

This will create a `vendor` folder with the required libraries.

### **Step 3: Create the `.env` File**

1. In the project directory, create a new file named `.env`.  
   Add your Outlook SMTP credentials:  
   SMTP_HOST=smtp.office365.com  
   SMTP_PORT=587  
   SMTP_USER= your-outlook-email  
   SMTP_PASS=your-outlook-password

**Note**: If you have multi-factor authentication (MFA) enabled on your Outlook account, use an app-specific password instead of your regular password.

---

## **How to Run the Application**

1. **Step 1: Ensure all requirements are met.**
   - PHP and Composer must be installed.
   - Dependencies (`PHPMailer` and `Dotenv`) should be installed in the project.
2. **Step 2: Configure the `.env` file.**
   - Enter your SMTP credentials in the `.env` file as shown in **Step 3**.
3. **Step 3: Open the `index.html` file in a browser.**
   - This file contains a simple form to collect recipient email, subject, and message.
4. **Step 4: Fill in the form fields.**
   - **Recipient Email**: The email address of the person you want to send the message to.
   - **Subject**: The subject of the email.
   - **Message**: The body content of the email.
5. **Step 5: Click the "Send Email" button.**
   - The form will send the data to `send_email.php` for processing.
6. **Step 6: Check for success or error messages.**
   - If everything is configured correctly, a success message will appear, and the recipient will receive the email.
   - If there are issues, error messages will help you identify the problem.

---

## **Troubleshooting**

1. **Issue 1: Composer not recognized.**  
   If you get an error like `composer: command not found`, ensure Composer is installed and added to your system’s PATH.
2. **Issue 2: Email not being sent.**
   - Double-check the SMTP credentials in the `.env` file.
   - Ensure that less secure apps are enabled for your Outlook account, or use an app-specific password if MFA is enabled.
3. **Issue 3: Missing `vendor/autoload.php`.**  
   If you see an error about `vendor/autoload.php` missing, ensure you have run `composer install` or `composer require phpmailer/phpmailer vlucas/phpdotenv` correctly.
4. **Issue 4: Permission issues with Git.**  
   If you encounter permission issues during installation, add the following to Git’s safe directory list:  
   git config \--global \--add safe.directory 'path/to/project'

---

## **Security Tips**

1. **Tip 1: Never commit your `.env` file to version control.**  
   Add `.env` to your `.gitignore` file:  
   echo ".env" \>\> .gitignore
2. **Tip 2: Use strong, unique passwords for your SMTP credentials.**

---

## **License**

This project is open-source and available under the MIT License.

---

For further questions or support, feel free to contact **Khaled Abumarasa**.
