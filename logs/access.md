# Apache Access Logs
Theses are Apache Access logs that shows what happens to the web server with a timestamp and shows for example gobuster and what error message the server gave. <br>
<img width="718" height="356" alt="Screenshot 2025-08-06 173850" src="https://github.com/user-attachments/assets/8b31d32b-76fd-492d-856f-04bbd4cd2075" /> <br>
The screenshot above is when SecEngine was in DetectionOnly mode so as you can see, the gobuster command executed was allowed as you can see the 200 which means we can access it. <br> 
<img width="726" height="265" alt="Screenshot 2025-08-06 174645" src="https://github.com/user-attachments/assets/852f2fa7-52fe-48fb-b407-334af5b84a2e" /> <br>
This screenshot above was when SecEngine was on, so you can see the 403 after the gobuster command which means that access is forbidden, so just some basic hardening helps stop someone from seeing hidden directories. 

