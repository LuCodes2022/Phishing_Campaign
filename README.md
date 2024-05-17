# Fishing Campaign

## Intro

### description of the exercise

This is an activity assigned by BeCode in order to learn how to run a targeted fishing campaign. In this project I will be using Linode Cloud (as VPS) and Gophish (as a phishing server).

### I am still working on:
- Spoofing my email

## Detailed explanation of the project's creation

### Creating the VPS

First we need to go to linode cloud and chose the appropriate plan for our needs. Make sure to remember the password you set in this step as ou will be prompted to enter it when trying to ssh into the server.

![](/assets/campaign_start.png)
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

### Gophish Campaign