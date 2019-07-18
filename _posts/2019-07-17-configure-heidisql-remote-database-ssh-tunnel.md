---
layout: post
title: Configure HeidiSQL to Access Remote Database via SSH Tunnel
---

Here's a quick guide on how to access a remote database in HeidiSQL using [SSH Tunnel](https://www.ssh.com/ssh/tunneling/example){:target="_blank"}, which is a mechanism in [SSH](https://www.ssh.com/ssh/){:target="_blank"} for tunneling application ports from the client machine to the server machine and vice versa.

Suppose HeidiSQL is already running, click on an existing session or create a new one by clicking the **New** button.

## Basic Settings

Under the **Settings** tab, do the following:

 - Set the **Network type** to `MariaDB or MySQL (SSH tunnel)`
 - Set the **Hostname / IP** to `127.0.0.1`
 - Set the **Port** to `3306`
 - Enter the database username and password credentials.
 - Select the remote database that you want to access. Leave it empty if you want to access all the databases on the remote server.

## SSH Tunnel Settings

Before continuing, make sure that you already have a `.ssh` folder in your home directory. If you don't, open your terminal or command line and run the following command:

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

That command will create a `.ssh` folder in your home directory and inside it, a new public/private SSH key pair will be created as well using the provided email address as a label.

When you're prompted to "Enter a file in which to save the key", just press `ENTER` to accept the default location which is your home directory. Afterwards, you'll be prompted to set a passphrase which is optional. Just hit `ENTER` if you don't want to set a passphrase.

Under the **SSH tunnel** tab, do the following:

- Set the **plink.exe location** to the path of the `plink.exe` executable file. You can download it [here](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html){:target="_blank"} if you don't have the file yet. It can be found under the **Alternative binary files** section.
- Set the **SSH host + port** to `192.168.123.0` as the host and `22` as the port. The `192.168.123.0` host IP address is just a placeholder, replace it with an actual one.
- Set the **Local port** to `3307`
- Enter the database username and password credentials.
- Increase or decrease the **plink.exe timeout** value or just leave the default value.
- Set the **Private key file** to the path of the `id_rsa.ppk` file. If you currently don't have one, download `puttygen.exe` [here](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html){:target="_blank"} in order to generate one. The executable file can be found under the **Alternative binary files** section.

  Run `puttygen.exe` and click the **Conversions** menu item and then click **Import key** and then select the `id_rsa` private key file. Afterwards, make sure that the **Type of key to generate** is set to `RSA` and also, you can enter a **Key passphrase** if you want. Click the **Generate** button when you're done.

Don't forget to click the **Save** button before you click **Open**, otherwise, you'll be repeating the process once you close and run HeidiSQL again.
