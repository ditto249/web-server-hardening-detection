# ModSecurity Audit Logs
## These are ModSecurity audit logs which shows what ModSecurity does to anything that happens to the server.
<img width="728" height="200" alt="Screenshot 2025-08-06 174726" src="https://github.com/user-attachments/assets/53f8bbe3-0e04-4181-9a72-4c1490c38503" /> <br>
In this screenshot above, you can see that ModSecurity is in enabled mode, and there is an Action that intercepted something, which was probably a gobuster command or a sqli. <br>
<img width="718" height="276" alt="Screenshot 2025-08-06 174034" src="https://github.com/user-attachments/assets/34fef9a8-974e-46f8-a6b5-0b34d520fe51" /> <br>
In this screenshot above, ModSecurity is in Detection Only, so it didn't do anything, but you can see there was something that it detected with the rule id "980170", which is a rule that doesn't directly block or detect attacks but rather contributes to the overall scoring and decision-making process within the WAF. 
