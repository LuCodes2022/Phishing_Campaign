# Fishing Campaign

## Intro

### description of the exercise

This is an activity assigned by BeCode in order to learn how to run a targeted fishing campaign. In this project I will be using Linode Cloud (as VPS) and Gophish (as a phishing server).

### I am still working on:
- Spoofing my email
- finessing this mardown file

## Detailed explanation of the project's creation

### Creating the VPS

First we need to go to linode cloud and chose the appropriate plan for our needs. Make sure to remember the password you set in this step as ou will be prompted to enter it when trying to ssh into the server.

![](/assets/phishinglinode.png)

After that is set up you should land on a page with your VPS info! 

### Setting up the environment

Next we will use the ssh command they provide us on the top right to have ssh access to our VPS.

![](/assets/ssh.png)

Now enter the command alongside the IP address corresponding to your VPS, once you are prompted to enter the password. 

After gaining ssh access, create a folder: 

```bash
mkdir gophish
```

Once you do you will want to go inside the folder and download gophish:

```bash
cd gophish
sudo apt update
sudo apt upgrade
sudo install unzip
```
Now we need to go online and look for the official gophish github, select the version compatible with your OS, and copy paste it into the following command:

```bash
sudo wget (link provided)
```
Extract the data from the file by running:

```bash
unzip gophish
```

Now we need to change the config.json file, make sure to replace the default home IP address with simply 0.0.0.0:333 (note we keep the same default port).

And to finish this section we now can run our gophish script:

```bash
sudo ./gophish
```

### Access VPS on your broswer of choice

Go to your broswer and enter http://IPgivenwhenrunninggophish:3333

You will be prompted the enter the credidentials given to you in your terminal, enter them.

Now you will be prompted to enter a new password.

Congrats! Now you can access your gophish server.

### Setting up an email for the campaign

I am going with outlook, therefore after creating my account, I go to my account info and click on security (make sure two actor authentifiction is activated). From there I select manage passwords, then click on app passwords click on create app password (this will be used in the next step to connect your gophish server and that email address).

![](/assets/create_app_password.png)

### Gophish

First we set up our sendin email address by clicking on that section and entering the relevant information:

![](/assets/sendingprofile.png)

Then we enter the information of the page we would like to use, you can either enter html in the designated area or import a website by clicking on import then entering the URL of the website you want to use:

![](/assets/landing.png)

Choose a URL you want the user to be redirected to after entering their information then click save page:

![](/assets/landing2.png)

Now let's select the email template by clicking on its section and entering the relevant info:

![](/assets/email_template.png)

Note that you can chose to either import the source code of an email or use your own stylized html content.

Now it is time to create a group and add the emails of the users we want to send the email to. click on add group, it will open a form where you can add users by clicking the add button then entering their information:

![](/assets/group.png)

And now we can start the campaign selecting the information provided earlier throughout the sections in our drop down menu.

![](/assets/campaign_start.png)

Your campaign has now started!

### Monitoring

You can check the status of your campaign by clicking on  dashboard:

![](/assets/dashboard1.png)
![](/assets/dashboard2.png)
