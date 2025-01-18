# Installing-Splunk-Enterprise

<h1> Splunk-Enterprise Installation - Prerequisites</h1>
This tutorial outlines the prerequisites and installation for Splunk Enterprise on a linux machine.<br />

<h2>Environments and Technologies Used</h2>

- AWS (Virtual Machines/Compute)
- SSH
  

<h2>Operating Systems Used </h2>

- Linux</b>

<h2>List of Prerequisites</h2>

- Create an AWS Account (free)
- Create a Splunk Account (free)

<h2>Installation Steps</h2>
<p> <img src="(https://i.imgur.com/8HaTcP2.jpeg)" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will start by logging in to your AWS Account. Search for LightSail Service in the search engine. Click on "Create Instance". Click on the OS only option. Choose Amazon Linux 2. I recommend choosing the free 90 day trial for individuals who are just getting started with Splunk. You will also need atlest 1-2 GB of RAM for your Splunk instance.
</p>

<p>
Now log in to your Splunk Account. From here select Products -> Platform -> Splunk Enterprise -> Get Started -> Free Trial. 
</p>
<p>
Choose Linux .tgz and click Download. You also need to copy  the Command Line (wget) and paste it into a sticky notes
</p>
<p>
Go back to AWS and click on your instance. Click “Connect using SSH”
</p>
<p>
Once you are on the command line type “sudo su”. This gives you root user ability. Then type in “passwd” and make a password. Type the password in again to lock in your password.
</p>
<p>
Type in “useradd splunk”. Type in “mkdir /opt/splunk”. This is making a new directory where you will put your splunk instance.
</p>

<p>
Then type “ cd /opt/”. You are changing the directory.
</p>
<p>
Take the copied wget link and paste it into the cmd line. It will now install your Splunk instance
</p>
