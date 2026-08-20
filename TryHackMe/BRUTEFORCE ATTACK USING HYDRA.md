# BRUTEFORCE ATTACK USING HYDRA
Hydra is tool that helps in guessing or checking the valid password pairs for a web app. It runs through a list and brute force the username and password for any authentication service. Hydra supports many services some of it includes http[s]-{head|get|post}, http[s]-{get|post}-form, http-proxy, ldap, SMTP, Oracle, Telnet etc.
For bruteforcing any service you need to custom write a command for it. There are some options for what can be include in that command. Some common are –l, and –p 
-l: Used when you know the username (-l <username>)
-L: This is used when you don’t know the username and try to guess it using a username list. (-L <FILE PATH>)
-p: Used when you know the password (-l <password>)
-P: This is used when you don’t know the password and try to guess it using a password list. (-L <FILE PATH>)
Service: 
We also write down the service we are using as well as their protocol and the IP of the machine. 
LAB PASSWORD ATTACK:
Before attacking any machine we need to know the exposed open ports on the machine so we ran nmap on the machine.

<img width="715" height="263" alt="image" src="https://github.com/user-attachments/assets/f1bee5af-6646-43be-aaa6-d96bdad0ef7c" />

Once we know the open ports then we proceed to attack them using hyrda. But first we make sure we have the wordlist require for the attack. If it’s zip then uzip it using sudo gzip –d usr/share/wordlists/rockyou.txt.gzs
<img width="975" height="411" alt="image" src="https://github.com/user-attachments/assets/b0dfe88a-3480-42cb-8663-05fa91f9f9ce" />

Once the file is unzipped we can move on to our command. From nmap we got 2 open ports. One is ssh and the other is http. For the ssh protocol attack we first give it a user name and path to the wordlist for password along the protocol and machine IP. HYDRA would now attack the ip with possible password pairs and retrieve us the password if available.
<img width="975" height="273" alt="image" src="https://github.com/user-attachments/assets/3d60b844-97cc-401d-96aa-278484e6b744" />

Here we have the password for molly is butterfly
We use this password to login into molly’s server:
<img width="820" height="603" alt="image" src="https://github.com/user-attachments/assets/038d9a27-3898-4200-95bc-2feb4246721c" />

Once in we can look search through the directory. Here we have the flag2.txt file which we access after logging in.
<img width="690" height="191" alt="image" src="https://github.com/user-attachments/assets/4c201903-d872-4376-ad2e-883ab8202485" />

Second port that was open was http, after checking the IP we find a form exiting on the page. We use burpsuite to capture the login request send to the server, and analyze the parameter written inside it.
<img width="418" height="460" alt="image" src="https://github.com/user-attachments/assets/7386dc00-d4fa-4f78-8f73-244ac83651e8" />

Once we have the parameter names we use hydra. We do the same process as ssh request, although instead of the ssh we use http-post-form (the service is an http service which is performing post operation and the webpage type is a form). Then we provide it with the end point /login (we know it from the webpage we visited) then we give it the username and password placeholder that hydra will swap out the password from wordlist at. 
<img width="975" height="108" alt="image" src="https://github.com/user-attachments/assets/856e9aaa-ce12-432c-8126-6f60cfdf2ea1" />


<img width="975" height="304" alt="image" src="https://github.com/user-attachments/assets/61dbf994-c26d-4e2e-96ae-a42b46c6a168" />
After the request is completed executing it have bought use multiple password that are valid for the user. We then try to use these password and judge which one is the correct one. Then we go back to the http IP address set username and password and it allows us the captured flag code.

<img width="449" height="519" alt="image" src="https://github.com/user-attachments/assets/518513d6-412a-4f62-ac5d-8d98ef80e235" />
