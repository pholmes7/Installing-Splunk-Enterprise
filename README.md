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

<h3>Setting up Lightsail</h3>
<p> <img src="https://i.imgur.com/enSfOoU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
You will start by logging in to your AWS Account. Search for LightSail Service in the search engine.<p>


<p> <img src="https://i.imgur.com/IdfRcug.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>Click on "Create Instance". <p>
  
<p> <img src="https://i.imgur.com/HOcMyiR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p> Underneath "Select a Platform" choose Linux/Unix. Click on the OS only option. Choose Amazon Linux 2. </p>

<p> <img src="https://i.imgur.com/BZy07ju.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p> Choose Dual Stack as your Network type. I recommend choosing the free 90 day trial for individuals who are just getting started with Splunk. You will also need atlest 1-2 GB of RAM for your Splunk instance.</p>

<p> <img src="https://i.imgur.com/IZwMON7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>Name your Instance. Then click Create Instance.</p>

<p> <img src="https://i.imgur.com/HmNSQ5R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p> Your instance is now being created. It should take 1 - 2 minutes for it to start running.</p>
<p>

<h3>Downloading Splunk</h3>
<p> <img src="https://i.imgur.com/shaonDB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p> <img src="https://i.imgur.com/cNBhsJd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>Now log in to your Splunk Account. From here select Products -> Platform -> Splunk Enterprise -> Get Started -> Free Trial. 
</p>

<p> <img src="https://i.imgur.com/ckZMKx2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>
Choose Linux .tgz. Copy the Command Line (wget) and paste it into a sticky note. Click Download.
</p>

<p> <img src="https://i.imgur.com/XXUNcLb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>
Go back to AWS and click on your instance. Click “Connect using SSH”
</p>

<p> <img src="https://i.imgur.com/jLRGet8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>
Once you are on the command line type “sudo su”. This gives you root user ability. Then type in “passwd” and make a password. Type the password in again to lock in your password.
</p>

<p> <img src="https://i.imgur.com/JKGYEA7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>
Type in “useradd splunk”. Type in “mkdir /opt/splunk”. This is making a new directory where you will put your splunk instance.
</p>

<p> <img src="https://i.imgur.com/JKGYEA7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>
Then type “ cd /opt/”. You are changing the directory.
</p>

<p> <img src="https://i.imgur.com/fwfncJ5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>
Take the copied wget link and paste it into the cmd line. It will now install your Splunk instance
</p>


<p> <img src="https://i.imgur.com/mkuLMVY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>  
<p>Type “ls” then copy the output into your sticky note.</p>

<p> <img src="https://i.imgur.com/aO6JmER.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>You have to un tar the file by replacing the given file with file path you just copied. Use tar xvzf “ your file path” -C /opt  </p>
<p>Copy the new cmd into your cmd line. You are now installing Splunk. </p>


<p> <img src="https://i.imgur.com/UO5Urb3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>Type “sudo /opt/splunk/bin/splunk start --accept-license”</p> 

<p> <img src="https://i.imgur.com/cChv1Sm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 

<p>It will ask for a username - put your first name

In the password portion - put “Password”</p> 

<p> <img src="https://i.imgur.com/Z1vsKYY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p> Once it done grab the Splunk Web Interface and paste it into your sticky note. </p>

<h3>Logging into Splunk Instance</h3>

<p> <img src="https://i.imgur.com/ZV9khkx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>Go to back to your Splunk Enterprise Instance with AWS. Click on Networking. </p>


<p> <img src="https://i.imgur.com/SCzo2zN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>Add a new rule. Click Custom → “All TCP” → Create. </p>
<p>In a real world environment - you wouldn’t do this because you are opening up every port. </p>

<p> <img src="https://i.imgur.com/EVSo0gK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>Go to sticky note and type in “http:// “your public IP”:8000”</p> 

<p> <img src="https://i.imgur.com/0R0CjJ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>Take that address and paste it into web browser. Now type in the username and password you used to create the Splunk instance earlier.</p>

<p> <img src="https://i.imgur.com/vib6MQk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p> 
<p>
Congrats you have created and installed a Splunk environment within a Linux VM!
</p>



