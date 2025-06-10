<img width="413" alt="Screenshot 2025-06-07 at 4 16 00 PM" src="https://github.com/user-attachments/assets/659cb78b-7adf-4dfa-86b5-f264ecebff34" /><img width="450" height="250" alt="Microsoft Active Directory Logo" src="https://github.com/user-attachments/assets/cd75c7f5-fba1-4682-a616-dc487e761fbc"
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
 - Did it work? Make sure you have no issues logging in!
</p>
<br />

<h3>🛠️ Step 2: Group Policy Objects</h3>

<p>
<img width="784" alt="Screenshot 2025-06-07 at 4 01 45 PM" src="https://github.com/user-attachments/assets/007241c6-6bd0-4a02-98da-668c2fe2d0ac" />

<img width="400" alt="Screenshot 2025-06-07 at 4 01 58 PM" src="https://github.com/user-attachments/assets/9432d18f-9d64-4980-a8bd-6695db15ce8a" />

<img width="401" alt="Screenshot 2025-06-07 at 4 02 12 PM" src="https://github.com/user-attachments/assets/6c475f03-39be-49b2-a8b4-8b35dcc0c82e" />
</p>

<p>- Log into DC-1 using jane_admin. (mydomain.com\jane_admin)</p>
<p>- Once logged in, right-click the Start Menu and select Run.</p>
<p>- Type in gpmc.msc and click OK.</p>
<br />

<p>
 <img width="827" alt="Screenshot 2025-06-07 at 4 03 52 PM" src="https://github.com/user-attachments/assets/d57c3f56-a2fd-490f-b644-1b0d22352314" />

 <img width="1224" alt="Screenshot 2025-06-07 at 4 06 12 PM" src="https://github.com/user-attachments/assets/3c1636fa-69ae-4d12-8d66-3b9f65938716" />
</p>

<p>
 - Under Domains -> mydomain.com -> right-click Default Domain Policy and select Edit. See Figure 2.
</p>
<p>
 - This will open the Group Policy Management Editor.
</p>
<br />


<p>
<img width="960" alt="Screenshot 2025-06-07 at 4 06 57 PM" src="https://github.com/user-attachments/assets/ef3306ad-3aad-4a2d-939d-732d2b2aaf6a" />
</p>


<p>
 - In Group Policy Management Editor click Computer Configuration -> Policies -> Windows Settings -> Security Settings -> Account Policies -> right click Account Lockout Policy -> click Open
</p>

<br />

<p>
<img width="958" alt="Screenshot 2025-06-07 at 4 07 28 PM" src="https://github.com/user-attachments/assets/915de0ac-3bf2-4411-a176-a7446b658c1d" />
<img width="418" alt="Screenshot 2025-06-07 at 4 07 36 PM" src="https://github.com/user-attachments/assets/e690dace-259c-40f3-94d2-8bf615b4e68b" />
<img width="421" alt="Screenshot 2025-06-07 at 4 07 48 PM" src="https://github.com/user-attachments/assets/742237b5-0b2b-4d7a-b792-7b55db9d4a91" />
</p>

<p>
 - Open Account lockout durtion Properties. The Account lockout duration Properties window will pop up. Check the box by "Define this policy setting", set it for 30 minutes, and click Apply and then click OK. 
</p>
<br />

<p>
<img width="628" alt="Screenshot 2025-06-07 at 4 08 07 PM" src="https://github.com/user-attachments/assets/f39f1c4e-51ee-456d-a128-eb7fca4a4496" />
</p>

<p>
 - The Suggested Value Changes window will pop up. Review the changes and click OK because we want them. 
</p>
<br />

<p>
<img width="961" alt="Screenshot 2025-06-07 at 4 08 49 PM" src="https://github.com/user-attachments/assets/3d12ada6-4e80-4f4e-a4eb-12c74c6d1fd1" />

<img width="419" alt="Screenshot 2025-06-07 at 4 08 59 PM" src="https://github.com/user-attachments/assets/67a30360-4e97-466b-8af6-1378166dafba" />
<img width="421" alt="Screenshot 2025-06-07 at 4 09 20 PM" src="https://github.com/user-attachments/assets/c637cbd8-d48e-43a0-b08f-925d4e26388e" />

</p>

<p>
 - Confirm the details of our updated Account Lockout Policy. 
</p>
<p>
 - Next we want to enable administrator account lockout
</p>
<p>
 - From "Allow Adminisgrator account lockout", open the Allow Administator account lockout properties window. Then check the box next to "Define this policy setting:" and then select "Enabled". Click "Apply" and then click "OK".
</p>
<p>
 - We have finished with our Group Policy changes. Usually, this should take about 90 minutes to take effect, but we are going to force update the policy so the changes take effect now.
</p>
<br />

<p>
<img width="785" alt="Screenshot 2025-06-07 at 4 10 44 PM" src="https://github.com/user-attachments/assets/cf6b4798-b462-4518-8ba2-a1c7f20436ce" />
<img width="979" alt="Screenshot 2025-06-07 at 4 11 01 PM" src="https://github.com/user-attachments/assets/4824a306-972e-4b2d-805e-fe0ba1d5ac8e" />
<img width="980" alt="Screenshot 2025-06-07 at 4 11 13 PM" src="https://github.com/user-attachments/assets/50e80b4c-0d54-45ab-9f82-c2ae175ac705" />
<img width="980" alt="Screenshot 2025-06-07 at 4 11 40 PM" src="https://github.com/user-attachments/assets/37b54012-7834-47b0-bc66-935f7e48e0f2" />
</p>

<p>
 - In Client-1 and log in as jane_admin. (mydomain.com\jane_admin) 
</p>
<p>
 - Open Command Prompt. Enter the command gpupdate /force. Press enter.
</p>
<p>
 - Once the force update is finished, log out of Client-1.
</p>
<br />

<p>
<img width="1012" alt="Screenshot 2025-06-07 at 4 13 32 PM" src="https://github.com/user-attachments/assets/5a680ace-91d0-46c7-b599-931a52565b61" />
<img width="1016" alt="Screenshot 2025-06-07 at 4 13 46 PM" src="https://github.com/user-attachments/assets/c0e165ef-af77-4565-9b45-ea0b940de467" />
</p>

<p>
 - Now, we are going to try to log into Client-1 as a user within the domain but with the wrong password 6 times. 
</p>
<p>
 - See what happens after too many invalid sign in attempts.
</p>
<br />

<p>
<img width="756" alt="Screenshot 2025-06-07 at 4 14 59 PM" src="https://github.com/user-attachments/assets/09937d4f-7f21-4203-ad31-ae916bb9102d" />
<img width="519" alt="Screenshot 2025-06-07 at 4 15 13 PM" src="https://github.com/user-attachments/assets/c3ab2071-f058-42d0-801f-f5894a7bd5c0" />

<img width="516" alt="Screenshot 2025-06-07 at 4 15 23 PM" src="https://github.com/user-attachments/assets/fec40cdc-53af-4141-a21d-7cb4d989902f" />

</p>

<p>
 - Log back on DC-1 as jane_admin (mydomain.com\jane_admin). Open up Active Directory Users and Computers.
</p>
<p>
 - Find the user (bal.lade) that we just locked out. Unlock the account. Right-click mydomain.com and select Find.</p>
<p>
 - Type in the username (bal.lade) and click "Find Now". You should see the user pop up under Search results.
</p>
<br />

<p>
<img width="413" alt="Screenshot 2025-06-07 at 4 15 49 PM" src="https://github.com/user-attachments/assets/8a256810-371c-4b64-9b6d-80a9b2a69a61" />
<img width="413" alt="Screenshot 2025-06-07 at 4 16 00 PM" src="https://github.com/user-attachments/assets/ec78813c-1445-48a6-ab46-b19d1713b39e" />
</p>

<p>
 - Double click the username under Search results and the account's Properties window should pop up.
</p>
<p>
 - Check the box next to Unlock account. Click "Apply", then click "OK".
</p>
<br />

<p>
<img width="1710" alt="Screenshot 2025-06-07 at 4 17 01 PM" src="https://github.com/user-attachments/assets/92fa90df-ca65-4f33-b6e2-0993aed25e53" />
<img width="788" alt="Screenshot 2025-06-07 at 4 18 41 PM" src="https://github.com/user-attachments/assets/1dcd5ead-075e-42d0-b2a2-c2c0abe17a5e" />
<img width="859" alt="Screenshot 2025-06-07 at 4 18 54 PM" src="https://github.com/user-attachments/assets/67c53492-440e-42a5-b3bc-56570a95abfe" />
</p>

<p>
 - Try log back into Client-1 as that same user now that it has been unlocked. (mydomain.com\bal.lade)</p>
<p>
 - (Optional) Open up Windows Powershell and type in the command whoami and press Enter. You should see the user's username appear.
</p>
<br />

<table>
  <tr>
    <td>
     <img width="755" alt="Screenshot 2025-06-07 at 4 20 25 PM" src="https://github.com/user-attachments/assets/56661588-ea66-4f1e-b382-d3bbf6d7005d" />
    </td>
    <td>
      <img width="516" alt="Screenshot 2025-06-07 at 4 21 02 PM" src="https://github.com/user-attachments/assets/143189be-1a76-4e45-81c7-ee0b5876549a" />
    </td>
  </tr>
</table>
<p>
 - Another thing we can do in Active Directory Users and Computers is disable accounts.
</p> 
<p>
 - We can disable the username that we just unlocked or a different one to vote them off of the domain.
</p>
<p>
 - Here are two different ways to disable an account, one uses Find, to search for the user, the other we look through _EMPLOYEES to find the user. Disable a user.
</p>
<br />

<p>
 <img width="1013" alt="Screenshot 2025-06-07 at 4 21 34 PM" src="https://github.com/user-attachments/assets/1b0805d2-d532-4bde-b9a2-bf13cf69bfad" />
</p>
<p>
 - See what happens when we try to log in as a disabled user. Go back and reenable the account.
</p>


<table>
  <tr>
    <td>
      <img width="755" alt="Screenshot 2025-06-07 at 4 22 13 PM" src="https://github.com/user-attachments/assets/19cb56af-23ee-4675-a008-1623ac3e4cb9" />
    </td>
    <td>
     <img width="517" alt="Screenshot 2025-06-07 at 4 22 29 PM" src="https://github.com/user-attachments/assets/cc71e4e7-772d-47d0-820c-2951f6b67699" />
    </td>
  </tr>
</table>
<p>
 - We can also reset passwords if needed from Active Directory Users and Computers.
</p> 
<p>- Same as before, The above images show how to reset passwords by scrolling through _EMPLOYEES and through Find. Let's reset a password</p>
<br />

<p>
 <img width="382" alt="Screenshot 2025-06-07 at 4 22 35 PM" src="https://github.com/user-attachments/assets/8c155ef9-d3ed-49c8-bcec-c5364e4a376d" />
 <img width="381" alt="Screenshot 2025-06-07 at 4 22 52 PM" src="https://github.com/user-attachments/assets/6575603a-30c2-4cc2-863a-9be2ca16b06c" />
</p>
<p>
 - Type in the new password under "New password:". Type it again under "Confirm password:". Click "OK" to reset the password.
</p>
<p>
 - Test the password reset by logging into the account. 
</p>

<p>
<img width="786" alt="Screenshot 2025-06-07 at 4 24 32 PM" src="https://github.com/user-attachments/assets/a9e4c209-e610-45a1-82fa-ed26b997d70f" />
<img width="788" alt="Screenshot 2025-06-07 at 4 25 17 PM" src="https://github.com/user-attachments/assets/48c44c35-a11d-46f9-9b7d-e7b0484a8dfb" />
<img width="1094" alt="Screenshot 2025-06-07 at 4 25 50 PM" src="https://github.com/user-attachments/assets/fdd9ad6e-c65a-413b-b80c-3f57a4b13f5f" />
<img width="1094" alt="Screenshot 2025-06-07 at 4 26 12 PM" src="https://github.com/user-attachments/assets/da64f0bc-3687-474b-9b1b-a8c4e816de4d" />
<img width="428" alt="Screenshot 2025-06-07 at 4 26 23 PM" src="https://github.com/user-attachments/assets/c1b7ec31-6698-4539-b5ec-e263ef9d3c08" />
<img width="1091" alt="Screenshot 2025-06-07 at 4 28 22 PM" src="https://github.com/user-attachments/assets/e9d1af72-5345-444e-91c6-5bae27ecebc0" />

 
</p>

<p>
 - Finally, before we end the project, log into Client-1 as jane_admin (mydomain.com\jane_admin) 
</p>
<p>
 - From the Start Menu, open up eventvwr.msc and click "Run as administrator".
</p>
<p>
 - The Event Viewer window will pop up.
</p>
<p>
 - Now we want to look at security logs. Expand Window Logs. 
</p>
<p>
 - Right-click Security -> click Find.
</p>
<p>
 -  Type in the username that was locked out earlier after too many incorrect sign in attempts (bal.lade).
<p>
 - Observe the logs and see the log in attempts the user made with timestamps.
</p>
<br />

<h2>Conclusion</h2>

<p>This concludes the project. We added maby users to the domain and set up some Group Policy Objects. Don't forget to Stop (turn off) the VMs in Azure once you're done! 
</p>
<br />







