# Lab: SQL injection UNION attack, determining the number of columns returned by the query
When SQL injection we don’t know the database schema. We guess the schema by writing and stuffing the query by commands that help us in define the table fields. Two command used here are Order by and Union.
## ORDER BY:
We inject the orderby command within the url. This is so we can guess how many columns are inside the table. We start the url filling with ORDER BY 1 and then we kept it increasing. When a numbered amount of column are present the request would respond with 200.

<img width="486" height="342" alt="image" src="https://github.com/user-attachments/assets/3b662266-6ec9-437f-a295-9e25e51442e6" />
<img width="480" height="342" alt="image" src="https://github.com/user-attachments/assets/4b64e580-0fde-4e79-9dd3-af9166cdc42c" />

And when the entered amount of columns are not present, the server would respond with the 500 internal server error.

<img width="488" height="342" alt="image" src="https://github.com/user-attachments/assets/790c6f61-2078-4b29-8cbf-af13dcd8f6a2" />

## UNION AND NULL:
Union is the second command that is used to determine the column of the database. It is a SQL command that is used to combine the result set of two or more select into a single set. We use Null with the union command and keep increasing the amount until we receive response code 200. 
Here we use two types of the filtering, one is when you need to guess the amount of column. The reason is the requirement that individual queries must return the same number of column. So the data can be fetched.

<img width="484" height="341" alt="image" src="https://github.com/user-attachments/assets/d8a58157-d509-4748-bf4c-e432356d1c6c" />
<img width="484" height="342" alt="image" src="https://github.com/user-attachments/assets/73f5d9c5-6e08-4532-abb6-d0e5ae2c2b4d" />

Second is when you guess the data type of the column to make sure you can find the correct data type of the field/column you want to hit.
<img width="975" height="462" alt="image" src="https://github.com/user-attachments/assets/5791d96b-8ae8-40bd-b778-08cf00068215" />
<img width="686" height="424" alt="image" src="https://github.com/user-attachments/assets/69ddb412-18c1-4e76-b979-f22e080464cd" />
<img width="979" height="293" alt="image" src="https://github.com/user-attachments/assets/190de31a-b2cb-4b10-a0b7-d4d438edd677" />
<img width="979" height="485" alt="image" src="https://github.com/user-attachments/assets/b00e4936-4dfe-40c3-aacd-93cc0b00543b" />
