---
layout: post
title: XAMPP Send Email from Localhost
---

If you happen to be using [XAMPP](https://www.apachefriends.org/index.html){:target="_blank"} as your development environment, the sending of emails via localhost will not work by default if not configured properly.

## php.ini

The first step is to modify a configuration file called `php.ini` located under `C:\xampp\php` unless you installed XAMPP on a different location, you need to do some adjustments.

Another way to locate the `php.ini` file is to create a PHP file under `C:\xampp\htdocs` and name it `phpinfo.php` and in this file, enter the following code:

```php
<?php echo phpinfo(); ?>
```

Save the file and visit [http://localhost/phpinfo.php](http://localhost/phpinfo.php){:target="_blank"} in your browser and search for **Loaded Configuration File** and from there you will see where the `php.ini` file is located on your hard drive.

Open the `php.ini` file and search for **sendmail_path**. It's commented out by default, so uncomment it by removing the semicolon at the beginning, set its value to `"\"C:\xampp\sendmail\sendmail.exe\" -t"` then save.

```
sendmail_path = "\"C:\xampp\sendmail\sendmail.exe\" -t"
```

## sendmail.ini

Modify the `sendmail.ini` file which is located under `C:\xampp\sendmail` and make the following changes accordingly:

```
smtp_server = smtp.gmail.com
smtp_port = 587
auth_username = YOUR_USERNAME@gmail.com
auth_password = YOUR_PASSWORD
```

Under `auth_username` and `auth_password`, make sure that it's a valid gmail account.

## Restart Apache Server

In order for changes to take effect, restart the Apache Server. There are many ways to do this, here's one way using the XAMPP Control Panel.

On the panel, click _Services_ and after that, right click on the _Apache2.4_ and click _Restart_.

## Send a Test Email

To wrap up, create a PHP file under `C:\xampp\htdocs` and name it `mail.php` and in this file, enter the following code:

```php
<?php
$recipient = 'YOUR_USERNAME@gmail.com';
$subject = 'Test Email';
$message = 'This is a test email.';
mail($recipient, $subject, $message);
?>
```

Change the `$recipient` to your gmail username and visit [http://localhost/mail.php](http://localhost/mail.php){:target="_blank"} in your browser.

You should receive the test email in your inbox.

----
