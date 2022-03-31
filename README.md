  <p align="center">
    A Powerful Ransomware Tool for Security Testing Used by ReadTeams
  </p>

## Prerequisites 🧰

* **Visual Studio 2019 or later** </br>

* **Xampp Server (Windows) or LAMP Server(Linux)** </br>

* **Ngrok for port forwarding** </br>

## SETUP AND RUNNING 🖥️

* ### Clone This Repo
   ```sh
   git clone https://github.com/Transmetal/Ransomware-pt1
   ```
* ### Webserver & Database 
   
    * **Copy the all the files in webpanel directory to htdocs or (/var/www/html)**  
	
	* **Open Mysql Shell** 
	
	* **Login as Root user** 
	```sh
     mysql -h localhost -u root
   ```
    * **Create new database & assign user**
	
	```sh
     CREATE DATABASE jasmin_db;
	 CREATE USER 'jasminadmin'@'localhost' IDENTIFIED BY '123456';
	 GRANT ALL PRIVILEGES ON jasmin_db.* TO 'jasminadmin'@'localhost';
	 Exit
   ```
	
	* **Importing jasmin_db.sql file from database directory** 
	
	```sh
      mysql -u jasminadmin -p123456 jasmin_db < htdocs/database/jasmin_db.sql
    ```
	* **Loggin Dashboard**
     
	 Open Google Chrome and visit http://localhost/ <br>
	 Use default credentials
	```sh
     Username    : siddhant
	 Access Code : 123456
    ```
	
* ### Generating Payload
         
    Note: You should have installed visual studio 2019 or later in your machine		 
	
	* **Use ngrok server for port forwarding (Wan Attack)**
	 
	```sh
     ngrok  http localhost:80
    ```
	
	* **Copy Forwarding Address** 
	
	* **Configure variables** <br>
         * =>   Inside **"Jasmin Encrypter"** directory open "Jasmin Encryptor.sln" file <br>
         * =>   Go to line number 34 & 35 <br>
	     * =>   Set Ngrok host address for **"hostaddr"** & **"AlertMsgLink"** Variable <br>
	
	* **Building .Exe File** <br>
	     * =>   Go to top nav bar & click to build => Clean Solution  <br>
         * =>   Again click to build => Clean Jasmin Encryptor <br>
	     * =>   Once Again click to build button => Rebuild Jasmin Encryptor <br>
		 * =>   Go to **"Jasmin Encryptor\bin\Release"** directory !! Congrats Payload is ready <br>
		 
* ### Next Steps	
    * **Sending File to Victim's Pc** <br>
	     * Replace the email address inside "webpanel/alertmsg.zip/index.html" <br>
	     * Now, Send this Payload file to your victims through emails or any socail other engineering technique you want <br>
		 * When Ever our victim click on that payload file it will encrypt all important files and send the decryption key to our web dashboard <br>
		 * For Custom alert message to your victims, edit the HTML file inside "webpanel/alertmsg.zip" <br>
		 
* ### Decryption Process			  
    * **Decrypting Victims File** <br>
	     * =>   open **"Jasmin decryptor\Jasmin decryptor.sln"** & build the .exe file <br>
         * =>   get the **SystemId** from your victims through emails  <br>
	     * =>   download the Decryption key from web-dashboard for that **SystemId** <br>
		 * =>   reply your victims with Decryption Tool and Passsword File  <br>
		 
<!-- LICENSE -->
## DISCLAIMER 
 * Codesiddhant is a Github Page related to Computer Security  and not a site that promotes hacking / cracking / software piracy. <br>
 * Do not attempt to violate the law with anything contained here. If you planned to use the tool for illegal purpose, then please leave this site immediately! We will not be responsible for your any illegal actions. Neither administration of this tool, the developer of this application, or anyone else affiliated in any way, is going to accept responsibility for your actions. <br>
 * You shall not misuse this tool to harm someone’s computer. However, you may try out these hacks on your own computer at your own risk. Simulating Ransomware attack (without permission) on computers that you do not own is illegal. <br>
 * We believe only in White Hat Hacking. On the other hand, we condemn Black Hat Hacking. <br>
 * **A ransomware attack is considered to be illegal activity aside from capturing your data in the computer, it will demand you to pay a ransom fee. Encrypting someone’s data without their written permission is a punishable offense** <br> 
