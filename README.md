<h1>📌 AWS EC‑2 Static Web Hosting</h1>

This repository provides a complete guide and working example for hosting a static website on Amazon EC2. It is designed for developers, students, and professionals who want to learn how to deploy lightweight web applications on AWS infrastructure without relying on managed services like S3 or Amplify. By following the instructions and using the included configuration files, you will gain hands‑on experience with EC2, Linux server administration, and web server setup.<br/>
The project begins with the launch and configuration of an EC2 instance, covering key aspects such as choosing the right AMI, configuring instance types, setting up SSH access, and managing security groups. Once the server is running, the repository demonstrates how to install and configure a web server (Apache or Nginx) to serve static files such as HTML, CSS, and JavaScript. The workflow includes uploading website assets, organizing directories, and ensuring proper permissions for smooth deployment.<br/>
Security is emphasized throughout the setup. You will learn how to configure inbound rules, restrict unnecessary ports, and manage firewall settings to protect your server. The repository also highlights cost‑optimization strategies, making use of AWS Free Tier resources wherever possible, so learners can experiment without incurring heavy charges.
Beyond basic hosting, the repository introduces scalability concepts such as load balancing and auto‑scaling groups, providing insight into how static sites can be extended for production environments. It also includes notes on monitoring, logging, and troubleshooting common deployment issues.<br/>
<h2>📂 Repository Structure</h2>
  <ul>
<li> README.md → Step‑by‑step setup guide</li>
<li> configs/ → Web server configuration files</li>
<li> website/ → Sample static site files</li>
    </ul><br/>
<h2>🚀 Use Cases</h2>
<ul><li> Hosting personal portfolios or blogs</li>
<li> Deploying business landing pages</li>
<li> Practicing AWS EC2 fundamentals for interviews and projects</li></ol>
<br/>
This repository is both a learning resource and a deployment template, enabling you to quickly spin up a static site on AWS EC2 while understanding the underlying mechanics of cloud hosting.
<br/>

<h2>State of instance:</h2>
<ul>
<li>Pending: The instance is in the process of being launched. You can't connect to it yet.</li>
<li>Running: The instance is fully operational and it is ready to use. You will be billed for its compute time while
it is in this state.</li>
<li>Stopping: The instance is in the process of shutting down.</li>
<li>Stopped: The instance is powered off. You will not be billed for the compute time, but you are still being billed
for the attached EBS volumes.</li>
<li>shutting-down: The instance is in the process of being terminated.</li>
<li>Terminated: The instance has been permanently deleted. All the data on this instance will be lost.</li>
<li>Rebooting: The instance is restarting.</li>
<li>Hibernating: This is a special state where RAM contents are being saved to the EBS root volumes before it
shuts down.</li>

<h2>Steps for the EC2 Static Web Hosting</h2>
<ul>
<li> Create the instance using any of the platform of Linux (Ubuntu, Amazon Linux).
<li> Download the .pem private key.
<li> Log in to the instance.
<li> Once after you log in, clone the statuc website repository from the GitHub to your instance.
<li> For deploying the application, we must install a web server called as "nginx".
</ol><br/>
->nginx: nginx is a webserver that excels at serving static content. Its primary job is to accept requests
from the web browser and find the requested files on a server and send them back.<br/>
  
To install nginx, first update the package manager and the install nginx.<br/>
<a>For Ubuntu:  sudo apt update (It will update the instance states)<br/>
   sudo apt install nginx(It will install the nginx in your instance)<br/>
   <ul>
     <li>After installing nginx, if it is not started or if it is not enabled then use this command<br/>
       <ul><li>For Ubuntu: sudo systemctl start nginx</li>
           <li>sudo systemctl enable nginx</li></ul>
     </li>
     <li>To deploy the application, we must copy our static website files in the correct directory
for the webserver to serve them.
       Command:  sudo cp -r ./static website repo name/* /var/www/html
     </li>
     <li>Copy the public ip address from AWS instance page and paste it in the searchbar of the browser<br/>
(If it doesn't load follow these steps:<br/>
       <ul>
         <li>Tick on the instance and go to the security options.</li>
         <li>Under security click on security group.</li>
         <li>Then click on edit inbound rules</li>
         <li>Click on add rule. Under that select HTTP and select anywhere ipu4 and then save the rules.</li>
         <li>Refresh the page and make https as http.</li>
       </ul>
     </li>
   </ul>
