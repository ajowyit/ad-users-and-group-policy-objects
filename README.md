<img width="1527" alt="Screenshot 2025-06-07 at 10 44 46 AM" src="https://github.com/user-attachments/assets/cdf00331-b26a-4946-ae01-ea7dc506f5a5" /><p align="center">
<img width="450" height="250" alt="Microsoft Active Directory Logo" src="https://github.com/user-attachments/assets/cd75c7f5-fba1-4682-a616-dc487e761fbc"
 alt="Microsoft Active Directory Logo"/>
</p>

<h1>Creating Users and Group Policy Objects for Active Directory</h1>
This tutorial outlines creating a User Database and Group Policy Objects for Active Directory within Azure Virtual Machines.<br />

<h2>Prerequisite</h2>

- [Create Active Directory Infrastructure in Azure](https://github.com/ajowyit/create-ad-infrastructure)
- [Deployment and Configuration of Active Directory in the Cloud](https://github.com/ajowyit/ad-deployment-configuration)

<h2>💻 Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Wndows App (for macOS)
- Remote Desktop/Windows App
- Active Directory Domain Services
- PowerShell

<h2>👨‍💻 Operating Systems Used </h2>

- macOS Sequoia
- Windows Server 2022
- Windows 10 (21H2)

<h2>🪜 High-Level Steps</h2>

- Section 1: Create a User Database
- Section 2: Group Policy Objects 

<h2>Deployment and Configuration Steps</h2>

<h3>🛠️ Step 1: Create a User Database</h3>

<p>
<img width="788" alt="Screenshot 2025-06-07 at 10 35 35 AM" src="https://github.com/user-attachments/assets/2883ce72-a9c8-4634-9861-084259803c08" />
<img width="457" alt="Screenshot 2025-06-07 at 10 37 17 AM" src="https://github.com/user-attachments/assets/4348781e-e580-4e46-a954-411723c1fe93" />

</p>

<p>
- Log in into DC-1 with Remote Desktop/Windows App with the jane_admin account. (mydomain.com\jane_admin and password)
</p>
<p>
 - From the Start Menu, type PowerShell in the search bar. Right-click Windows PowerShell ISE. Then click "Run as Admin".
</p>
<p>
 A window will pop up asking if you want to allow this app to make cahnges to your device. Click "Yes" to run Windows PowerShell ISE.
</p>
<br />

<p>
 <img width="938" alt="Screenshot 2025-06-07 at 10 42 41 AM" src="https://github.com/user-attachments/assets/644a7238-2ee8-4e78-98e7-d0c974f61a8f" />

</p>
<br />

- Click here --> [SCRIPT](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1) to copy the file we need to create our user database.

<p>
 - Click the icon next to Raw in the top right corner to copy the raw file. Go back to PowerShell ISE.</p>
<br />

<p>
<img width="1527" alt="Screenshot 2025-06-07 at 10 44 46 AM" src="https://github.com/user-attachments/assets/7f248dbc-65e2-450c-a6e9-1f2e1b160b8a" />
<img width="1527" alt="Screenshot 2025-06-07 at 10 45 17 AM" src="https://github.com/user-attachments/assets/90b6a857-7040-4d20-ae19-728d306e2128" />
<img width="1525" alt="Screenshot 2025-06-07 at 10 45 31 AM" src="https://github.com/user-attachments/assets/f4c78441-817d-4400-a504-9bcdaaa666e5" />
<img width="1523" alt="Screenshot 2025-06-07 at 10 45 53 AM" src="https://github.com/user-attachments/assets/5a8d10a8-c930-4048-8174-69bbcd99b38e" />
</p>

<p>
 - In PowerShell ISE, click the blank page icon at the top.
</p>
<p>
 - Paste in the script you copied in the space that pops up.
</p>
<p>
 - Click the green play button icon at the top to run the script. We should be able to see the users being created after we start running the script.
</p>
<br />

<p>
<img width="1523" alt="Screenshot 2025-06-07 at 10 45 53 AM" src="https://github.com/user-attachments/assets/81a56a20-cfef-4b22-adc7-bc6bdebcb79d" />
</p>

<p>
 - While the users are being created, take a note of the password in the 2nd line of the script. This it the password for all the users we are creating in the database. We will need this when we try to log in as one of the new users.
</p>
<br />

<p>
<img width="789" alt="Screenshot 2025-06-07 at 11 02 45 AM" src="https://github.com/user-attachments/assets/1e20f028-d063-4c4c-9dc4-ccc403a8caa8" />
<img width="978" alt="Screenshot 2025-06-07 at 11 03 07 AM" src="https://github.com/user-attachments/assets/d6883871-4ab5-4fc6-ba86-186c3d49b451" />
<img width="752" alt="Screenshot 2025-06-07 at 11 03 19 AM" src="https://github.com/user-attachments/assets/0dbcdf59-4ef5-47c8-96ce-8f725d5c03d1" />
<img width="751" alt="Screenshot 2025-06-07 at 11 03 42 AM" src="https://github.com/user-attachments/assets/0cd4947d-ea9e-4ae4-8d92-359642c79585" />
</p>

<p>
 - Once the script is finished running, from the start menu, open Active Directory Users and Computers.</p>
<p>
 - A window will pop up saying something about items in the _EMPLOYEES folder were retrieved. Click "OK".
</p>
<p>
 - Select the _EMPLOYEES folder to see all the users created so far. Optionally, click the refresh icon at the top to put them in alphabetical order.
</p>
<br />

<p>
<img width="751" alt="Screenshot 2025-06-07 at 11 03 49 AM" src="https://github.com/user-attachments/assets/6b57e726-1cff-40ef-b86c-c7fcaee38943" />

</p>

<p>
 - Choose username you like and let's use it to login to Client-1.
</p>
<p>
 - I chose bag.pap
</p>
<br />

<p>
<img width="1015" alt="Screenshot 2025-06-07 at 11 04 37 AM" src="https://github.com/user-attachments/assets/02723e39-555e-4346-8e80-dc78f78bd972" />
<img width="1708" alt="Screenshot 2025-06-07 at 11 04 48 AM" src="https://github.com/user-attachments/assets/9e0a7417-82f0-4ae1-b377-39fbe4af3fff" />
</p>

<p>
 - Now attempt to login to Client-1 with the new user you chose.
</p>
<p>
 - Make sure you specify domain in username. (mydomain.com) 
</p>
<p>
 - mydomain.com\bag.pap and Password1. (mydomain.com\username and Password1) 
</p>
<p>
 - Did it work? Once we have sucessfully logged in, we have now ensured that we were successful in creating a user database with many users!
</p>
<br />

<h3>🛠️ Step 2: Group Policy Objects</h3>

<p>
<img width="600" alt="GP2" src="https://github.com/user-attachments/assets/d6583ac0-b04e-496f-b2ff-0ada114649c7" />
</p>

<p>- Log into DC-1 using jane_admin. (mydomain.com\jane_admin)</p>
<p>- Once logged in, right-click the Start Menu and select Run.</p>
<p>- Type in gpmc.msc and click OK.</p>
<br />

<p>
<img width="750" alt="GP3" src="https://github.com/user-attachments/assets/62ddd1e6-4715-4a35-960a-b116522a93d4" />
</p>

<p>- Under mydomain.com, right-click Default Domain Policy and select Edit. See Figure 2.</p>
<p>- This will open the Group Policy Management Editor.</p>
<br />


<p>
<img width="900" alt="GP4" src="https://github.com/user-attachments/assets/84693f7b-2243-42ab-8834-ea704aa31074" />
</p>

<p>- We will need to expand a couple things to find the right path. Here we go. See Figure 3</p>
<p>- In Group Policy Management Editor -> Computer Configuration -> Policies -> Windows Settings -> Security Settings -> Account Policies.</p>
<p>- Now, open Account Lockout Policy.</p>
<br />

<p>
<img width="900" alt="GP6" src="https://github.com/user-attachments/assets/6cd2af20-a548-4ac7-9645-11bad27e19c8" />
</p>

<p>- Open Account lockout durtion Properties. Check the box by Define the policy, set for 30 minutes, and click Apply and OK. </p>
<br />

<p>
<img width="900" alt="GP7" src="https://github.com/user-attachments/assets/44552a31-91f1-42e5-ac6c-a4881d0ebca0" />
</p>

<p>- Notice the Suggested Value Changes based off our lockout duration. </p>
<p>- We want this, so simply click OK. </p>
<br />

<p>
<img width="900" alt="GP8" src="https://github.com/user-attachments/assets/4f6d968b-2ba2-438a-b546-e4d0da50014a" />
</p>

<p>- We can confirm the details of our updated Account Lockout Policy here. </p>
<p>- I think this takes almost 90 minutes to take effect, but we are not waiting that long because we got stuff to do. </p>
<p>- Next, we will force update the policy so the changes take effect now.</p>
<br />

<p>
<img width="750" alt="GP9" src="https://github.com/user-attachments/assets/b558ed54-2f8b-4174-8b17-32d5502f48bb" />
</p>

<p>- Jump over to Client-1 and log in as jane_admin. (mydomain.com\jane_admin) </p>
<p>- Open Command Prompt, enter the command gpupdate /force  and press enter.</p>
<p>- Once the force update is complete, log out of Client-1.</p>
<br />

<p>
<img width="550" alt="GP10" src="https://github.com/user-attachments/assets/c3be8dc3-5884-412e-8f8f-d09bdcd2a2ee" />
</p>

<p>- Now, we are going to log into Client-1 as another user within the domain but with the wrong password. </p>
<p>- Attempt 6 logins with the wrong password and see what happens.</p>
<p>- YOU SHALL NOT PASS! 🧙🏽‍♂️</p>
<br />

<p>
<img width="750" alt="GP11" src="https://github.com/user-attachments/assets/b54b14ec-de92-45e6-9bed-ffe1893c9e78" />
</p>

<p>- Lets get back on DC-1 as jane_admin (mydomain.com\jane_admin) and navigate to Active Directory Users and Computers.</p>
<p>- We need to find the user (jus.pob) that we just locked out and unlock their account. You can open _EMPLOYEES and scroll for days, depending on what the username is, or right-click mydomain.com and select Find.</p>
<p>- This will be a lot faster.</p>
<br />

<p>
<img width="750" alt="GP13" src="https://github.com/user-attachments/assets/88bce577-435f-4c5a-bbd0-06c57c3b2cf3" />
</p>

<p>- Enter the username and click Find Now. (jus.pob is who I'm looking for).</p>
<p>- Click on the username when it appears in the Search results below. Under the Account tab we will find that the user's account is Locked out of the AD Domain Controller as shown in Figure 10.</p>
<p>- Check the box next to Unlock account, click Apply, and then OK.</p>
<br />

<p>
<img width="750" alt="GP13 1" src="https://github.com/user-attachments/assets/d21d27bf-60c2-4c6c-9de7-8c33b6756f5e" />
</p>

<p>- Now that the account has been unlocked, try log back into Client-1 as that same user. (mydomain.com\jus.pob)</p>
<p>- You will know right a way if it worked or not. I went to PowerShell after logging on and entered "whoami". See figure 11.😆  </p>
<br />

<table>
  <tr>
    <td>
      <img width="1000" alt="GP14" src="https://github.com/user-attachments/assets/67b863ca-28f6-4b05-8e9e-cf7904863144" />
    </td>
    <td>
      <img width="1000" alt="GP15" src="https://github.com/user-attachments/assets/82732951-dcda-47e3-b783-e585b4be4803" />
    </td>
  </tr>
</table>
<p>
 - We can do a bunch of stuff with the user accounts in Active Directory Users and Computers. We can disable accounts if needed. Although that might be more of a HR thing, but you never know.</p> 
<p>- You can disable the username that we just unlocked or pick one you don't like and vote them off the domain. 🤣</p>
<p>- Then, try to log into Client-1 as the exiled user and see what happens.
<p>- Figure 12 shows the long way to find the user and Figure 13 shows the express lane.</p>
<br />

<table>
  <tr>
    <td>
      <img width="1000" alt="GP16" src="https://github.com/user-attachments/assets/731c7e88-3356-4bdd-baf5-9c41ea9a7659" />
    </td>
    <td>
      <img width="1000" alt="GP17" src="https://github.com/user-attachments/assets/5a349fb3-fb8d-4b41-a61c-eeafe64a9705" />
    </td>
  </tr>
</table>
<p>
 - We can also reset the password if needed. For example, during the account lockout scenario earlier, when we unlocked the account we would have reset the password and then had the user create a new password for security reasons. </p> 
<p>- Same as before, Figure 14 shows the long way to find the user and Figure 15 shows the express lane.</p>
<br />

<p>
<img width="750" alt="GP18" src="https://github.com/user-attachments/assets/8e309698-4ff9-4e39-9a2e-897e4a4d46d0" />
</p>

<p>- One last thing before we end this project. Log into Client-1 as jane_admin (mydomain.com\jane_admin) </p>
<p>- From the Start Menu, search eventvwr.msc and Open as Admin. </p>
<p>- This will take us to the Event Viewer and allow us to look at Security Logs.</p>
<p>- Expand Window Logs -> right-click Security -> click Find. Type in the username that was locked out earlier. (jus.pob)</p>
<p>- We can view the logs and see how many log in attempts the user made with timestamps.</p>
<br />

<h2>Conclusion</h2>

<p>This concludes our project.  We added a ton of users to the domain and setup some Group Policy Objects. Playing a Domain Admin is pretty interesting and we barley scratched the surface. Don't forget to Stop (turn off) the VMs in Azure. As always, Thank You for your time and viewing this Project. We'll see you on the next one! 😎      
</p>
<br />







