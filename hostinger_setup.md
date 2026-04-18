# Hostinger Deployment Instructions - Dhuruv Detailing Studio

Follow these steps to deploy and configure your professional contact form on Hostinger.

## 1. Prepare PHPMailer Library
Hostinger shared hosting usually doesn't have SSH/Composer access enabled by default. To install PHPMailer manually:
1. Download the latest PHPMailer source code from GitHub: [PHPMailer GitHub](https://github.com/PHPMailer/PHPMailer) (Click 'Code' -> 'Download ZIP').
2. Extract the ZIP on your computer.
3. Use Hostinger's **File Manager** (hPanel) or an FTP client (like FileZilla) to create a folder named `PHPMailer` in your public_html directory.
4. Upload the following from the extracted PHPMailer folder into your server's `PHPMailer/src/` directory:
   - `Exception.php`
   - `PHPMailer.php`
   - `SMTP.php`

## 2. Configure SMTP Password
1. Log in to your Hostinger hPanel.
2. Go to **Emails** -> **Email Accounts**.
3. Ensure `sales@dhuruvcaraccessories.in` is created. If not, create it.
4. Open `send.php` in the Hostinger File Manager editor.
5. Find the line: `$smtpPassword = 'YOUR_PASSWORD_HERE';`
6. Replace `YOUR_PASSWORD_HERE` with your actual email password.
7. Save the file.

## 3. Verify SMTP Settings
The script is pre-configured for Hostinger:
- **Host**: `smtp.hostinger.com`
- **Port**: `465`
- **Security**: `SSL` (SMTPS)

## 4. File Structure Check
Ensure your files are uploaded as follows:
```text
/public_html
  ├── contact.html
  ├── send.php
  ├── style.css
  ├── script.js (if used, or logic is in contact.html)
  ├── images/
  │     └── logo.jpg
  └── PHPMailer/
        └── src/
              ├── Exception.php
              ├── PHPMailer.php
              └── SMTP.php
```

## 5. Final Test
1. Visit `https://dhuruvcaraccessories.in/contact.html`.
2. Fill out the form with a test email.
3. Check your `sales@dhuruvcaraccessories.in` inbox for the lead.
4. Check your test email inbox for the auto-reply.

---
**Note**: If you see an error about "Invalid email password", double check that you can log in to webmail with those credentials first.
