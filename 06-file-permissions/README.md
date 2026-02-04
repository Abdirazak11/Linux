<h2>File Permissions Management in Linux</h2>

<h3>Introduction to File Permissions</h3>
<p>
Linux file permissions determine who can <strong>read</strong>, <strong>write</strong>, or
<strong>execute</strong> files and directories. Every file and directory has permissions
assigned to three categories of users:
</p>

<ul>
  <li><strong>Owner (User)</strong> – The creator of the file</li>
  <li><strong>Group</strong> – Users belonging to the assigned group</li>
  <li><strong>Others</strong> – All other users on the system</li>
</ul>

<p>Permissions are represented as:</p>
<ul>
  <li><strong>Read (r or 4)</strong> – View file contents</li>
  <li><strong>Write (w or 2)</strong> – Modify file contents</li>
  <li><strong>Execute (x or 1)</strong> – Run scripts or programs</li>
</ul>

<hr>

<h3>Viewing File Permissions</h3>

<p>To check file permissions, use:</p>

<pre><code>ls -l filename</code></pre>

<p>Example output:</p>

<pre><code>-rwxr--r-- 1 user group 1234 Mar 28 10:00 myfile.sh</code></pre>

<p>
This shows permissions for the owner, group, and others respectively.
</p>

<hr>

<h3>Changing Permissions with <code>chmod</code></h3>

<h4>Using Symbolic Mode</h4>
<p>
Symbolic mode uses letters and symbols to modify permissions:
</p>

<ul>
  <li><code>+</code> Add permission</li>
  <li><code>-</code> Remove permission</li>
  <li><code>=</code> Set exact permission</li>
</ul>

<pre><code>chmod u+x filename     # Add execute permission for user
chmod g-w filename     # Remove write permission for group
chmod o=r filename     # Set read-only for others
chmod u=rwx,g=rx,o= filename
</code></pre>

<hr>

<h4>Using Numeric (Octal) Mode</h4>
<p>
Each permission has a numeric value:
</p>

<ul>
  <li>Read = 4</li>
  <li>Write = 2</li>
  <li>Execute = 1</li>
</ul>

<pre><code>chmod 755 filename   # User (rwx), Group (r-x), Others (r-x)
chmod 644 filename   # User (rw-), Group (r--), Others (r--)
chmod 700 filename   # User (rwx), No access for others
</code></pre>

<hr>

<h3>Changing Ownership with <code>chown</code></h3>

<p>Modify file owner and group:</p>

<pre><code>chown newuser filename
chown newuser:newgroup filename
chown :newgroup filename
</code></pre>

<p>Recursively change ownership:</p>

<pre><code>chown -R newuser:newgroup directory/</code></pre>

<hr>

<h3>Changing Group Ownership with <code>chgrp</code></h3>

<pre><code>chgrp newgroup filename
chgrp -R newgroup directory/
</code></pre>

<hr>

<h3>Special Permissions</h3>

<h4>SetUID (s)</h4>
<p>
Allows users to run a file with the file owner's permissions.
</p>

<pre><code>chmod u+s filename</code></pre>

<p>Example: <code>/usr/bin/passwd</code></p>

<hr>

<h4>SetGID (s)</h4>
<p>
Files run with the group’s permissions. Directories cause new files to inherit the group.
</p>

<pre><code>chmod g+s filename
chmod g+s directory/
</code></pre>

<hr>

<h4>Sticky Bit (t)</h4>
<p>
Ensures only file owners can delete their files within a directory.
</p>

<pre><code>chmod +t directory/</code></pre>

<p>Example: <code>/tmp</code></p>

<hr>

<h3>Default Permissions with <code>umask</code></h3>

<p>
The <code>umask</code> defines default permissions for newly created files and directories.
</p>

<pre><code>umask</code></pre>

<p>Set a new umask:</p>

<pre><code>umask 022</code></pre>

<p>
This results in:
</p>
<ul>
  <li>Directories: <code>755</code></li>
  <li>Files: <code>644</code></li>
</ul>

<hr>

<h3>Conclusion</h3>
<p>
Understanding Linux file permissions is essential for system security and proper access
control. Using <code>chmod</code>, <code>chown</code>, and <code>chgrp</code>, administrators can
efficiently manage file ownership and permissions across the system.
</p>
