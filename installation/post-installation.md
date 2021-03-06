# Post-Installation Setup

After initializing the website and database, there are a few more steps to be done before you can fully use MantisBT.

---

## 1. Security Setup

...

---

## 2. Email Setup

To use MantisBT, email must first be configured. We'll choose Simple Mail Transfer Protocol (SMTP) for this guide.

---

### 2.1. SMTP Port

- Port 25

Port 25 is the default tranmission channel for internet email assigned in RFC 821 by the Internet Engineering Task Force (IETF).

Nowadays, this port should only be used if you had set up your own mail server.

- Port 465

Port 465 was not officialy assigned as a SMTP tranmission channel by the IETF, but was instead recognized as one by the Internet Assigned Numbers Authority (IANA) to have an SMTP port using SSL.

Port 465, as of now, was recently reassigned by IANA to be used for another service, though it could still be used as an SMTP tranmission channel.

- Port 587

Port 587 is currently the default mail submission port. Port 587 can be used with TLS. We'll be using this port for our guide.

---

### 2.2. The Gmail SMTP Server

This guide will have the Gmail SMTP Server for our email tranmission setup.

- Gmail Outgoing Mail (SMTP) Server: smtp.gmail.com
- Requires SSL: Yes
- Requires TLS: Yes (if available)
- Requires Authentication: Yes
- Port for SSL: 465
- Port for TLS/STARTTLS: 587
- Account Name, User name, or Email address: Your full email address
- Password: Your Gmail password

Inferring from the information above, we can see that port 465 or 587 must be used. 

Information of Gmail SMTP Server taken from [Gmail Help Center](https://support.google.com/mail/answer/7126229?hl=en).

---

### 2.3. Email Address for Your Team

It's preferred to create an email address for MantisBT to use. As this guide aims to use Gmail SMTP Server, instructions to allow an Google Account to be used by MantisBT will be provided.

After creating/ or having prepared a Google email address for your team, navigate to the Security section of the Google Account settings.

Ensure that 'Allow less secure apps' is enabled (there should be a warning).

---

### 2.4. Configuration

1. Navigate to the php folder from your XAMPP folder. Make sure the .ini has the following line under Module Settings:

```js
extension=php_openssl.dll
```

2. Navigate to the config folder from your MantisBT root. Open 'config_inc.php' with a text-editor program.

3. Add the following configurations, under the existing configurations.

Enable registration and password reset:

```js
$g_allow_signup = ON;
$g_send_reset_password = ON;
```

Enable email notification:

```js
$g_enable_email_notification = ON;
```

Choose SMTP method to send mail:

```js
$g_phpMailer_method = PHPMAILER_METHOD_SMTP;
```

Choose Gmail SMTP server for sending mail:

```js
$g_smtp_host = 'smtp.gmail.com';
```

Choose TLS protocol for SMTP:

```js
$g_smtp_connection_mode = 'tls';
```

Choose Gmail SMTP port for TLS:

```js
$g_smtp_port = 587;
```

Choose email address to be used as sender:"

```js
$g_smtp_username = 'yourteam@gmail.com';
```

Give password for the email address:

```js
$g_smtp_password = 'emailpassword';
```

Choose email address to be shown on the website:

```js
$g_webmaster_email = 'yourteam@gmail.com';
```

This configuration doesn't matter when SMTP method is used, however, it is required to pass the installation check:

```js
$g_from_email = 'yourteam@gmail.com';
```

The name displayed to the recipient:

```js
$g_from_name = 'Your Team Name';
```

Choose email address to receive bounced email:

```js
$g_return_path_email = 'yourteam@gmail.com';
```

Here are all the configurations in one block:

```js
$g_allow_signup = ON;
$g_send_reset_password = ON;
$g_enable_email_notification = ON;
$g_phpMailer_method = PHPMAILER_METHOD_SMTP;
$g_smtp_host = 'smtp.gmail.com';
$g_smtp_connection_mode = 'tls';
$g_smtp_port = 587;
$g_smtp_username = 'yourteam@gmail.com';
$g_smtp_password = 'emailpassword';
$g_webmaster_email = 'yourteam@gmail.com';
$g_from_email = 'yourteam@gmail.com';
$g_from_name = 'Your Team Name';
$g_return_path_email = 'yourteam@gmail.com';
```

### 2.5. Test sending email

After configuring SMTP Server for MantisBT, on your browser, access the below url and click 'Send Mail' to run an email sending test.

```md
<your_server>/<your_mantis>/admin/email_queue.php
```

Check your team email address inbox to verify that the email was sent successfully.

---

## 3. Administration Configuration

Access the below url and login using the default administrator account.

```md
<your_server>/<your_mantis>/login_page.php
```

- Username: administrator
- Password: root

Next up is configuring the administrator acount, the default administrator account shouldn't be used after initial setup for security measures.

With that in mind, let's create a new administrator account. Navigate to Manage > Manage Users > Create New Account.

Enter required information, the email address shouldn't be your team email address. It could be your personal or business email address.

Set the 'Access Level' of the account to 'administrator'.

Make sure 'Enabled' is checked.

On the other hand, 'Protected' shouldn't be checked, a protected account indicates a shared account, for example a guest/demo account.
Such account won't be able to change any account settings.

Press 'Create Account' to create an administrator account for your team.

After verifying that the account had been created, navigate to the default administrator account and disable (un-check 'Enabled') or delete ('Delete User' button) it.

Finally, logout of the default administrator account and login with your newly-created administrator account.

---

## 4. Installation Check

After finish setting up the administrator account, on your browser, access the below url to review the installation.

```md
<your_server>/<your_mantis>/admin/check/index.php
```

Keep in mind that the non-italic messages in the tests are not facts. They should be understood as 'checking if X is true'.

---

## Next steps

If there are no failed tests, you can now use MantisBT for your team.

Check out some other documents for some basic run-downs of MantisBT core features or try them out yourself.
