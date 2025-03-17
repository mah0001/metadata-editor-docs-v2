# Email configurations

For the Metadata Editor to function correctly it is important that this step be completed.

Many of the functions within the Editor, such as registration, forgot password require that the Editor be able to send emails to users. 


## Configure email

The email settings are stored in the config file `application/config/email.php`. The following settings are required to configure email:

```

$config['useragent']        = 'PHPMailer';
$config['protocol']         = 'smtp';
$config['smtp_host']        = 'outlook.office365.com';
$config['smtp_auth']        = true;
$config['smtp_user']        = 'your-email-address@outlook.com'; //email or username
$config['smtp_email']       = 'your-email-address@outlook.com'; //email address to send from
$config['smtp_pass']        = 'your-email-account-password';
$config['smtp_port']        = 1025;
$config['smtp_crypto']      = 'tls';

```

**SMTP_HOST:** Your SMTP server host name 

**SMTP_AUTH:** Set it to true if your SMTP server requires authentication (username and password) 

**SMTP_USER:** Email address or user name. If your email server require a username for authentication, type the username, otherwise fill in with the email address

**SMTP_EMAIL:** Email address same as in SMTP_USER

**SMTP_PASS:** Email password, if required. Otherwise, leave it empty

**SMTP_PORT:** Port number used by your email server. e.g. 25, 587, 443

**SMTP_CRYPTO:** Encryption to use. Options are `tls`, `ssl` or leave it empty if none is required


Once you have updated the configurations, save the file.


**Test the email settings**
i
The quickest way to test if the email settings are working is to use the “forgot password” option from the user login page. 

*	If you are already Logged in, log out and then go to the forgot password page. 

*	Enter the administrator or any other accounts email address that you know have an account in the Editor.

*	If the email failed, you will see an error message indicating that the email was not sent.


**Test email settings using site admin tool**

The Editor site administration includes a page to test email settings. Open the site administration, go to `settings` menu and open the last option `SMTP settings` and click on `Test email configurations`.

If you have filled in the email configurations (`application/config/email.php`), the page will read all settings from there. Otherwise, fill the email settings and press the button `Send email` to see if your settings are correct. The page will print detailed messages for both success and failed emails.


