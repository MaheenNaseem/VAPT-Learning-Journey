# Task: To reveal the hidden data existing on the website
<img width="979" height="69" alt="image" src="https://github.com/user-attachments/assets/3ccdf263-f30e-4fe1-8b04-af9ec7f4136c" />

<img width="739" height="468" alt="image" src="https://github.com/user-attachments/assets/acb48281-ee71-4590-b298-5b9427baecc0" />


When we open corporate gifts only some of the items from the list are shown, the full url of the site include a reveled=1 parameter which is the source of hiding the items.But we try to override it using sql injection such as ‘ or 1=1 - -‘, here’s what the command is doing.
It first ignores the query at gift, the or is the logical operator to execute the command only when one of the conditions are true and we already have 1=1 which is a truth. In the end we have - -  which tell the server to ignore whatever the command is after it, here it is the revealed parameter and in result the server shows us all the items.

<img width="979" height="132" alt="image" src="https://github.com/user-attachments/assets/ce12cbf4-06ea-49bf-807c-a8c70d4570cb" />

<img width="739" height="417" alt="image" src="https://github.com/user-attachments/assets/ae0241a3-8f85-4906-9265-de01c59bbf6e" />
