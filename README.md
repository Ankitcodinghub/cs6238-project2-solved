# cs6238-project2-solved



**<span style='color:red'>TO GET THIS SOLUTION VISIT:</span>** https://www.ankitcodinghub.com/product/cs6238-secure-computer-systems-project2-solved/

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;127589&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;4&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (4 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS6238 Project2 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
<div class="kksr-stars">
    
<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
    
<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>
                

<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (4 votes)    </div>
    </div>
<h1><a name="_Toc11318"></a>Project II: Strengthening Login Security with Two-Factor Authentication (2FA)</h1>
<h2><a name="_Toc11319"></a>Learning Objectives:</h2>
This project aims to enhance password security by incorporating a second authentication factor (2FA). We’ll explore this concept by modifying the Linux login implementation. While the specific implementation may be simplified for educational purposes, the underlying principles are similar to password hardening techniques discussed in class. Here’s what you’ll learn:

<ol>
<li><strong>Password-Based Authentication:</strong> Understand how traditional login systems with usernames and passwords work.</li>
<li><strong>Strength in Numbers:</strong> Explore the benefits of using multiple factors for stronger authentication compared to passwords alone.</li>
<li><strong>Building a Stronger Login:</strong> Modify the existing login code to incorporate an additional authentication factor.</li>
<li><strong>Security Analysis:</strong> Evaluate the effectiveness of the implemented 2FA system and identify potential limitations.</li>
</ol>
<strong>Focus:</strong>

This project concentrates on improving login security for local desktops/laptops. However, the concepts can be extended to secure remote logins as well.

&nbsp;

<h2><a name="_Toc11320"></a>Project Setup:</h2>
We’ll be using a pre-configured Ubuntu virtual machine (VM) compatible with Oracle VM VirtualBox 7.0. You can directly import this VM into VirtualBox for your work.

The VM has a pre-created user account named “cs6238” with standard user privileges. To access files requiring root access, open a terminal and type:

<ul>
<li>sudo su</li>
</ul>
Enter the password for “cs6238” (<strong>note:</strong> the password itself is not shown here for security reasons). Once you have root access, locate the desired file.

<strong>Default Credentials:</strong>

<ul>
<li>Username: cs6238</li>
<li>Password: cs6238 <strong>Accessing Project Files:</strong></li>
</ul>
<ol>
<li>Log in to the “cs6238” account.</li>
<li>Navigate to your desktop directory:</li>
</ol>
<ul>
<li>cd /home/cs6238/Desktop</li>
</ul>
<ol start="3">
<li>Clone the project repository from GitHub:
<ul>
<li>git clone https://github.com/TA-gatech/Project2.git</li>
</ul>
</li>
</ol>
<strong>Project Files:</strong>

The cloned repository contains:

<ul>
<li>Two Python code files: py and create_user.py</li>
<li>One executable: token_generator</li>
</ul>
&nbsp;

Figure 1. Desktop folder Content

&nbsp;

&nbsp;

<strong>Important Note:</strong>

<ul>
<li>It’s recommended to take snapshots of your VM before starting and while progressing through the project to prevent accidental data loss.</li>
</ul>
<strong>Understanding Linux Login System (Pre-requisite):</strong>

Before proceeding, familiarize yourself with the following aspects of the Linux login system:

<ol>
<li>How are users created in Linux?</li>
<li>What algorithms are used for password encryption/hashing?</li>
<li>Where is information derived from passwords stored?</li>
<li>How does the system check if a correct password is provided by a login request?</li>
<li>Why and how is salt used?</li>
<li>Who has access to the file containing password-related information?</li>
</ol>
There are plenty of online resources for these topics. The “GETTING STARTED ON LINUX LOGIN/PASSWORDS” section in the Appendix can serve as a starting point.

We’ve provided two Python code files to help you understand how the system works for creating and logging in users:

<ol>
<li><strong>py:</strong> This script creates a new user. Analyze its code to understand:
<ul>
<li>What it does o Requirements for successful execution o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Changes made to the /etc/shadow file after creating a user</li>
</ul>
</li>
<li><strong>py:</strong> This script verifies user login credentials (username and password). By analyzing its code, learn:
<ul>
<li>How user validation works after providing the correct password</li>
<li>How it retrieves the hash from the shadow file and compares it with the one generated from the user-provided password</li>
</ul>
</li>
</ol>
Once you understand these scripts, you’re ready for the main project task.

&nbsp;

<h2><a name="_Toc11321"></a>Task 1: Implementing 2FA (80% of grade)</h2>
This task focuses on implementing a 2FA system using a provided token_generator (TG) executable. While typical 2FA systems use a unique device per user (like a phone), this project uses a single TG for all user accounts. Each user will have two accounts: one in the 2FA system and one with the TG (registered with a PIN).

<h3><a name="_Toc11322"></a>Token Generator (TG):</h3>
You are provided with the compiled token_generator executable. You <em>do not</em> need to implement it; you only need to understand its interface and use it as a black box.

The TG offers three options:

<ul>
<li><strong>‘1’ (Register User):</strong>
<ul>
<li>Prompts for a user-id and a six-digit PIN. o Generates an initial token (IT) and creates an encrypted file named after the user-id.</li>
<li>Deleting this file effectively deletes the user’s TG account.</li>
</ul>
</li>
<li><strong>‘2’ (Generate Tokens):</strong>
<ul>
<li>Requires the user-id and correct PIN.</li>
<li>Returns the current token (CT) and the next token (NT).</li>
</ul>
</li>
<li><strong>‘3’ (Delete User):</strong>
<ul>
<li>Requires the user-id and correct PIN. o Returns the current token (CT) and deletes the user’s account and associated file.</li>
</ul>
</li>
</ul>
<strong>Important TG Behavior:</strong>

After each TG operation, the TG will prompt for confirmation. If the corresponding 2FA operation is successful, enter ‘y’ or ‘Y’. Otherwise, entering any other character will cause the TG to revert to its previous state.

<h3><a name="_Toc11323"></a>The 2FA Method:</h3>
The 2FA method involves four main operations: creating a user, logging in, updating, and deleting a user.

<ol>
<li><strong>Create User:</strong>
<ul>
<li>Requires: username (U), password (P, confirmed), salt, and the initial token (IT) from the TG.</li>
<li>The PIN for the TG and the password for the 2FA system <em>can be different</em>. The username for the 2FA system and the user-id for the TG <em>must be the same</em>. o The hardened password is created by concatenating the password (P) and the initial token (IT): P+IT. This hardened password is then hashed and stored in the /etc/shadow</li>
</ul>
</li>
<li><strong>Login:</strong>
<ul>
<li>Requires: username (U), password (P), current token (CT), and next token (NT) from the TG.</li>
<li>The system checks if the user exists. o The hardened password is created by concatenating the password (P) and the current token (CT): P+CT. o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; This hardened password is used to verify against the stored hash in</li>
</ul>
</li>
</ol>
/etc/shadow.

<ul>
<li>If successful, a new hardened password is created by concatenating the password (P) and the next token (NT): P+NT. This new hardened password is hashed, and the /etc/shadow file is updated with this new hash.</li>
<li>The TG confirmation mechanism is used to finalize or revert the changes.</li>
</ul>
<ol start="3">
<li><strong>Update:</strong>
<ul>
<li><strong>Update:</strong> Requires username (U), password (P), new password (NP, confirmed), new salt (NS), current token (CT), and next token (NT).</li>
</ul>
</li>
<li><strong>Delete:</strong> Requires username (U), password (P), and current token (CT).
<ul>
<li>These operations should be implemented based on the same principles as the login functionality.</li>
</ul>
</li>
</ol>
<h3><a name="_Toc11324"></a>Implementation of the 2FA method:</h3>
<strong>Important:</strong> Adhere to the specified prompt order. Regrade requests based on incorrect prompt order will not be accepted.

You must create a standalone Python program (2FA.py) based on the provided Python code. Your program must implement the following:

<ol>
<li><strong>User Prompting (10 pts):</strong></li>
</ol>
o &nbsp;&nbsp;&nbsp;&nbsp; Prompt the user to select an action:

▪ &nbsp;&nbsp;&nbsp;&nbsp; Select an action:

<ol>
<li>Create a user</li>
<li>Login</li>
<li>Update password</li>
<li>Delete user account</li>
</ol>
<ul>
<li>Do not loop into the action request. Once one action is selected the python script exits.</li>
</ul>
<ol start="2">
<li><strong>Creating Users (20 pts):</strong>
<ul>
<li>Prompt for Username, Password, Confirm Password, Salt, and Initial Token</li>
</ul>
</li>
</ol>
(IT).

<ol>
<li>Username: Alice</li>
<li>Password: Alice123</li>
<li>Confirm Password: Alice123</li>
<li>Salt: salt0123</li>
<li>Initial Token: 3Q.vPs40</li>
</ol>
<ul>
<li>If the user already exists, display “FAILURE: user &lt;username&gt; already exists” and exit. <em>Prompt all the information before checking if the user exists.</em> o If the user does not exist, create the user. This involves updating the</li>
</ul>
/etc/shadow and /etc/passwd files and creating a home directory. o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; On success, print “SUCCESS: &lt;user-id of the user&gt; created”. o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The salt remains the same unless the user updates the password or deletes and recreates the account.

<ol start="3">
<li><strong>Login (20 pts):</strong>
<ul>
<li>Request Username, Password, Current Token (CT), and Next Token (NT).
<ol>
<li>Username: Alice</li>
<li>Password: Alice123</li>
<li>Current Token: 3Q.vPs40</li>
<li>Next Token: iGxl329/ugOeSnhOzYE1B/</li>
</ol>
</li>
<li>Execute the 2FA login process. o On success, display “SUCCESS: Login Successful”. o &nbsp; If the user does not exist, display “FAILURE: user &lt;username&gt; does not exist”. <em>Prompt all the information before checking if the user exists.</em> o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; If the password or token is incorrect, display “FAILURE: either passwd or token incorrect.”</li>
</ul>
</li>
<li><strong>Password Update (15 pts):</strong></li>
</ol>
o &nbsp;&nbsp; Request Username, Password, New Password, Confirm New Password, New Salt, Current Token (CT), and Next Token (NT).

<ol>
<li>Username: Alice</li>
<li>Password: Alice123</li>
<li>New Password: New-Password</li>
<li>Confirm New Password: New-Password</li>
<li>New Salt: salt3210</li>
<li>Current Token: 3Q.vPs40</li>
<li>Next Token: iGxl329/ugOeSnhOzYE1B/</li>
</ol>
<ul>
<li>On success, display “SUCCESS: user &lt;username&gt; updated”.</li>
<li>Implement similar error handling as the login functionality.</li>
</ul>
<ol start="5">
<li><strong>Deleting a User (15 pts):</strong></li>
</ol>
o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Request username, password, and current token.

<ol>
<li>Username: Alice</li>
<li>Password: Alice123</li>
<li>Current Token: Gxl329/ugOeSnhOzYE1B/</li>
</ol>
<ul>
<li>If the values are correct, remove all user entries and the home directory. o On success, display “SUCCESS: user &lt;username&gt; Deleted”.</li>
<li>Implement similar error handling as the login functionality.</li>
</ul>
<strong>Important Considerations:</strong>

<ol>
<li>Token transfer between your 2FA implementation and the TG is manual (copypaste).</li>
<li>Use the appropriate TG option (‘1’, ‘2’, or ‘3’) when interacting with the TG.</li>
</ol>
<h2><a name="_Toc11325"></a>Task 2: Security Analysis of 2FA (20% of grade)</h2>
Perform a security analysis of the implemented 2FA method, addressing the following points:

<ul>
<li><strong>Advantages (2):</strong> Discuss two advantages of the implemented 2FA scheme compared to traditional password-only authentication.</li>
<li><strong>Disadvantages (2):</strong> Discuss two disadvantages or limitations of the implemented 2FA scheme.</li>
<li><strong>Possible Attacks (2):</strong> Describe two potential attacks that could be carried out against the implemented 2FA scheme.</li>
<li><strong>Improvement for Real-World Implementation:</strong> Assuming this 2FA system were to be deployed in a real-world environment, recommend one significant improvement to enhance its security.</li>
<li><strong>Server-Client Implementation and Secure Token Transfer:</strong> Explain how this 2FA scheme could be implemented in a server-client architecture. Detail how you would secure the transfer of tokens between the client and the server.</li>
</ul>
&nbsp;

<h2><a name="_Toc11326"></a>Project deliverables for your 2FA implementation:</h2>
<ol>
<li><strong>Python Script (2FA.py):</strong></li>
</ol>
This file should contain your Python code implementing the 2FA functionality based on the provided description. It should handle user prompts, and perform the necessary security checks during user creation, login, update, and deletion operations.

<ol start="2">
<li><strong>Security Analysis Report (gtid_2FA.pdf):</strong></li>
</ol>
This PDF report, named according to your GT ID (e.g., jrodriguez_2FA.pdf), should detail the security analysis of the implemented 2FA system. It should address:

<ul>
<li><strong>Task 2: Security Analysis of 2FA</strong> o <strong>Advantages (2):</strong> o <strong>Disadvantages (2):</strong> o <strong>Possible Attacks (2):</strong> o <strong>Improvement for Real-World Implementation:</strong></li>
</ul>
o &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <strong>Server-Client Implementation and Secure Token Transfer:</strong>

By covering these points in your report, you’ll demonstrate a comprehensive understanding of the 2FA system’s security implications and potential improvements.

<strong>Important Notes:</strong>

<ul>
<li>Remember to adhere to the prompt order while implementing the 2FA functionality in your Python script.</li>
<li>Ensure your report clearly addresses the security analysis points mentioned above.</li>
</ul>
&nbsp;

<strong>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </strong><strong>&nbsp;</strong>

<h1><a name="_Toc11327"></a>Appendix &nbsp;<sub>&nbsp;</sub><sub>&nbsp;</sub></h1>
<h3><a name="_Toc11328"></a>1. VirtualBox VMs</h3>
o &nbsp;&nbsp; If you’re unfamiliar with importing VMs, refer to the provided Oracle VM VirtualBox documentation:

<a href="https://docs.oracle.com/cd/E26217_01/E26796/html/qsimport-vm.html">https://docs.oracle.com/cd/E26217_01/E26796/html/qsimport</a><a href="https://docs.oracle.com/cd/E26217_01/E26796/html/qsimport-vm.html">–</a><a href="https://docs.oracle.com/cd/E26217_01/E26796/html/qsimport-vm.html">vm.html</a>

&nbsp;

<h3><a name="_Toc11329"></a>2. Figures</h3>
<strong>&nbsp;</strong>

Figure 1: Creating an Account

&nbsp;

Figure 2: Logging into an Account

&nbsp;

<h3><a name="_Toc11330"></a>3. Getting started on Linux Login and Passwords.</h3>
<strong>Linux User Creation and Password Storage:</strong>

When creating a new user, the Linux system prompts for a password. Depending on the Linux distribution and its configuration, one of several hashing algorithms is used for password encryption. The system generates a random salt, which is then used to create a one-way hash of the password. This hash, along with other user details, is stored in the /etc/shadow file.

<strong>Example User Entry in /etc/shadow:</strong>

cs6238:$6$Cl7HxrVPp7LvCHDb$km3WARvkSdd7toH5lS/OoU5mlSk4.F9ImoQ8H 5Cy5ii10klGO5TCTy9tOZCZFRko6EGM1uIEtwn2f6MN8MLA8/:19589:0:99999:

7:::

<strong>Structure of a User Entry:</strong>

Each user entry in /etc/shadow consists of nine fields separated by colons (:).

<ol>
<li><strong>Username:</strong> The user’s login name (e.g., cs6238).</li>
<li><strong>Password Hash:</strong> The encrypted password. This field itself contains three sub-fields separated by dollar signs ($):
<ul>
<li><strong>Algorithm Identifier:</strong> Indicates the hashing algorithm used. In the example, 6 denotes SHA-512.</li>
<li><strong>Salt:</strong> The random salt value used during hashing (Cl7HxrVPp7LvCHDb in the example).</li>
<li><strong>Hashed Password:</strong> The actual hash of the password combined with the salt (km3WARvkSdd7toH5lS/OoU5mlSk4.F9ImoQ8H5Cy5ii10klGO5TCTy9tOZCZ FRko6EGM1uIEtwn2f6MN8MLA8 in the example).</li>
</ul>
</li>
<li><strong>Last Password Change Date:</strong> Number of days since the epoch (January 1, 1970 UTC) when the password was last changed.</li>
<li><strong>Minimum Password Age:</strong> Minimum number of days before the password can be changed again.</li>
<li><strong>Maximum Password Age:</strong> Maximum number of days before the password must be changed.</li>
<li><strong>Warning Period:</strong> Number of days before password expiration when the user is warned.</li>
<li><strong>Inactive Period:</strong> Number of days after password expiration before the account is disabled.</li>
<li><strong>Account Expiration Date:</strong> Absolute date when the account expires.</li>
<li><strong>Reserved:</strong> Reserved for future use.</li>
</ol>
<strong>User Account Information in /etc/passwd:</strong>

After storing the password hash in /etc/shadow, the system creates a home directory for the new user and adds an entry to the /etc/passwd file. This file stores essential user account information needed during login. Each line in /etc/passwd represents a user account.

<strong>Example User Entry in /etc/passwd:</strong>

cs6238:x:1000:1000:cs6238:/home/cs6238:/bin/bash

<strong>Structure of a User Entry:</strong>

Each entry in /etc/passwd consists of seven fields separated by colons (:):

<ol>
<li><strong>Username:</strong> The user’s login name (e.g., cs6238).</li>
<li><strong>Password:</strong> Historically, this field contained the encrypted password. However, for security reasons, it now almost always contains an “x,” indicating that the actual password hash is stored in the /etc/shadow file.</li>
<li><strong>User ID (UID):</strong> A unique numerical identifier for the user (e.g., 1000).</li>
<li><strong>Group ID (GID):</strong> A numerical identifier for the user’s primary group (e.g., 1000).</li>
<li><strong>User Information (GECOS):</strong> Optional descriptive information about the user (e.g., the user’s full name, office location, etc.). In the example, it’s the same as the username.</li>
<li><strong>Home Directory:</strong> The absolute path to the user’s home directory (e.g., /home/cs6238).</li>
<li><strong>Login Shell:</strong> The absolute path to the user’s default command shell (e.g., /bin/bash).</li>
</ol>
<strong>Project Relevance:</strong>

For this project, it is sufficient to understand the basic structure and purpose of the /etc/passwd file, especially the username and home directory fields. Further exploration of the details of the /etc/passwd file is encouraged but not strictly required for completing the project.

<strong>User Creation Completion:</strong>

After updating the entry in the /etc/passwd file and creating the user’s home directory, the user creation process is complete.

&nbsp;
