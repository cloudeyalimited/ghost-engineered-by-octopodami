# Ghost Engineered by OCTOPODAMI (GEBO) Setup

Our pre-configured stack runs on AWS EC2 and gives you a complete Ghost site on one server. You can add other AWS services, such as S3, CloudFront, and Route 53, later.

## Preliminary Setup

You need to create a unique EC2 Key Pair so you can log into your EC2 instance easily. Within the AWS Management Console:

1. Go to **EC2** > **Network & Security** > **Key Pairs**
2. Click **Create Key Pair**
3. Enter a Key pair name and click **Create**
4. Download your Key pair with a **.pem** extension and store it in a safe place on your computer.

## Launch Instance

Within the EC2 Dashboard page, you can do the following to launch a Ghost Engineered by OCTOPODAMI (GEBO) instance:

1. Click the **Launch Instance** button or click this button [![Launch Stack](./images/launch-stack.png?raw=true)](https://aws.amazon.com/marketplace/pp/prodview-o5aotteozjq4m)
2. Next, click the **AWS Marketplace** tab on the left side of the **Choose an Amazon Machine Image (AMI)** page
3. Enter the phrase **octopodami** in the search box and press **enter** on your keyboard
4. Click the **select** button in front of Ghost Engineered by OCTOPODAMI®
5. Click the **continue** button in the dialog box
6. Select an instance type to fit your budget then click the **Review and Launch** button
7. Configure these options (**Security Groups**, **Instance Details**, **Storage**, and **Tags**) to match your business needs
8. Click the **launch** button

Wait about 10 minutes. The first boot installs Node.js, MySQL, and Ghost, then creates the owner account.

## Unlock Your Site

Within the EC2 Dashboard page, click **Instance** to view your running instance, if any.

1. Select the instance you launched to view its detailed descriptions
2. Click the icon in front of **IPv4 Public IP** to copy the IP Address of the server to clipboard
3. Paste the IP Address in your browser (Chrome, Firefox, and IE. e.t.c.)
4. You will be presented with the screen below:

![Octopodami Instance ID|512x397, 20%](./images/octopodami_initial_screen.jpg?raw=true "Octopodami Instance ID")

5. Copy the **Instance ID** from your EC2 dashboard, paste it in the input field and click the **Unlock Octopodami®** button to proceed
6. Your Ghost site opens in the same browser. The unlock lasts for one year, or until you clear your cookies

## Find Your Admin Credentials

Ghost is installed during the first boot, so there is no setup wizard to complete. The owner password is generated at random and stored on the server.

1. SSH into the server (see below)
2. Run `sudo cat /root/.ghost-credentials`
3. The file shows the admin email, admin password, database details, and site URLs
4. Open `http://<your ip address>/ghost/` and sign in with the admin email and password
5. Change the owner password after your first login

## Visit Your Ghost Site

You can now preview your new Ghost site at the IP Address of the server. The admin area can be accessed at **128.57.48.454/ghost/**

**Please Note**: the IP Address above is not a real one; yours will be unique. :wink:

Use the credentials from the server to access Ghost admin. You can now publish posts, install themes, and configure your site.

![Rejoice](https://media.giphy.com/media/26xBFFYvGNMfPo9QQ/giphy.gif?raw=true "Rejoice")

## Wanna Geek Out? SSH Into The Server

To SSH into your EC2 instance:

1. ```cd``` to the location of your .pem key
2. Run ```chmod 600 mykey.pem``` to lock down your SSH key
3. Run ```ssh -i /path/my-key-pair.pem ec2-user@<your ip address>```
4. Bam!!! Have fun. Don't break anything, but if you do. Support is available [here](mailto:tech@cloudeya.org).
5. To retrieve your Ghost credentials, run: ```sudo cat /root/.ghost-credentials```
6. To follow the installation, run: ```sudo tail -n 200 /var/log/ghost-install.log```
7. To check the services, run: ```systemctl status nginx mysqld ghost --no-pager```

## Links

1. [Marketplace Listing](https://aws.amazon.com/marketplace/pp/prodview-o5aotteozjq4m)
2. [EULA](./octopodamiEULA.txt)
3. [Knowledgebase](https://github.com/cloudeyalimited/ghost-engineered-by-octopodami/-/wikis/home)
4. [Issue Tracking](https://github.com/cloudeyalimited/ghost-engineered-by-octopodami/-/issues)
5. [Changelog](./changelog.md)

## Support

[Email](mailto:tech@cloudeya.org) support is available to Amazon Web Services Marketplace Customers. We do not offer refunds, but you may terminate your Ghost Engineered by OCTOPODAMI (GEBO) Stack at any time.

## License

The documentation is published under [BSD 3-Clause License](license.txt).

## Copyright

(c) 2020 - 2026 [Cloudeya Limited](https://cloudeya.org).
