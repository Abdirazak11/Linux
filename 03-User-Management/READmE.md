<h2>User Management in Linux</h2>

<h3>Introduction to User Management in Linux</h3>
<p>
Linux is a multi-user operating system, meaning multiple users can operate on a system
simultaneously. Proper user management ensures security, controlled access, and overall
system integrity.
</p>

<h3>Key Files Involved in User Management</h3>
<ul>
  <li><code>/etc/passwd</code> – Stores user account details</li>
  <li><code>/etc/shadow</code> – Stores encrypted user passwords</li>
  <li><code>/etc/group</code> – Stores group information</li>
  <li><code>/etc/gshadow</code> – Stores secure group details</li>
</ul>

<h3>Creating Users in Linux</h3>

<h4>useradd Command (Most Linux Distributions)</h4>

<p>Create a user without a home directory:</p>
<pre><code>useradd username
</code></pre>

<p>Create a user with a home directory:</p>
<pre><code>useradd -m username
</code></pre>

<p>Specify a shell for the user:</p>
<pre><code>useradd -s /bin/bash username
</code></pre>

<h4>adduser Command (Debian-Based Systems)</h4>
<p>
The <code>adduser</code> command is interactive and prompts for a password and user details.
</p>
<pre><code>adduser username
</code></pre>

<h3>Managing User Passwords</h3>

<p>Set or change a user’s password:</p>
<pre><code>passwd username
</code></pre>

<h4>Enforcing Password Policies</h4>

<p>Set password expiration (e.g., 90 days):</p>
<pre><code>chage -M 90 username
</code></pre>

<p>Lock a user account:</p>
<pre><code>passwd -l username
</code></pre>

<p>Unlock a user account:</p>
<pre><code>passwd -u username
</code></pre>

<h3>Modifying Users</h3>

<p>Change the username:</p>
<pre><code>usermod -l new_username old_username
</code></pre>

<p>Change the home directory:</p>
<pre><code>usermod -d /new/home/directory -m username
</code></pre>

<p>Change the default shell:</p>
<pre><code>usermod -s /bin/zsh username
</code></pre>

<h3>Deleting Users</h3>

<p>Delete a user but keep the home directory:</p>
<pre><code>userdel username
</code></pre>

<p>Delete a user and their home directory:</p>
<pre><code>userdel -r username
</code></pre>

<h3>Working with Groups</h3>

<h4>Creating Groups</h4>
<pre><code>groupadd groupname
</code></pre>

<h4>Adding Users to Groups</h4>
<pre><code>usermod -aG groupname username
</code></pre>

<h4>Viewing Group Memberships</h4>
<pre><code>groups username
</code></pre>

<h4>Changing Primary Group</h4>
<pre><code>usermod -g new_primary_group username
</code></pre>

<h3>Sudo Access and Privilege Escalation</h3>

<h4>Adding a User to the Sudo Group</h4>

<p>Debian-based systems:</p>
<pre><code>usermod -aG sudo username
</code></pre>

<p>RHEL-based systems:</p>
<pre><code>usermod -aG wheel username
</code></pre>

<h4>Granting Specific Commands with Sudo</h4>

<p>Edit the sudoers file safely:</p>
<pre><code>visudo
</code></pre>

<p>Add the following entry:</p>
<pre><code>username ALL=(ALL) NOPASSWD: /path/to/command
</code></pre>
