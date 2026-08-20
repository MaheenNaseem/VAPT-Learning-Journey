# TASK: bypass login as an administrator and update email
In the username field we will try to open admin account using SQL injection.
We first write the username and then we use ‘ - - so the server will treat whatever is written as a comment and would ignore it.

<img width="651" height="304" alt="image" src="https://github.com/user-attachments/assets/313e6a5e-2377-420b-b711-1364f4ab637d" />

<img width="979" height="67" alt="image" src="https://github.com/user-attachments/assets/0b620c3c-185b-4c01-896a-3960a6e26067" />

Once the attacker is logged in, it can perform anything just like here the attacker can update the email of admin account. 

<img width="438" height="204" alt="image" src="https://github.com/user-attachments/assets/82eaeb7f-82fe-43e5-9237-ed894f48e672" />
<img width="522" height="204" alt="image" src="https://github.com/user-attachments/assets/88ab6820-55d8-4f8e-96ca-e55b053abaf9" />

<img width="651" height="145" alt="image" src="https://github.com/user-attachments/assets/cffc5d91-514b-487c-9809-f68f5fbbae5c" />
