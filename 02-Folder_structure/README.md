<h2>Understanding the Folder Structure</h2>

<h3>Explanation of System Directories</h3>
<h4>Symbolic Links (Less Significant)</h4>

<table>
  <thead>
    <tr>
      <th>Directory</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/sbin → /usr/sbin</td>
      <td>System binaries for administrative commands (linked to /usr/sbin).</td>
    </tr>
    <tr>
      <td>/bin → /usr/bin</td>
      <td>Essential user binaries (linked to /usr/bin).</td>
    </tr>
    <tr>
      <td>/lib → /usr/lib</td>
      <td>Shared libraries and kernel modules (linked to /usr/lib).</td>
    </tr>
  </tbody>
</table>

<h3>Important System Directories</h3>

<table>
  <thead>
    <tr>
      <th>Directory</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/boot</td>
      <td>Stores files needed for booting the system (not relevant in containers).</td>
    </tr>
    <tr>
      <td>/usr</td>
      <td>Contains most user-installed applications and libraries.</td>
    </tr>
    <tr>
      <td>/var</td>
      <td>Stores logs, caches, and temporary files that change frequently.</td>
    </tr>
    <tr>
      <td>/etc</td>
      <td>Stores system configuration files.</td>
    </tr>
  </tbody>
</table>

<h3>User &amp; Application-Specific Directories</h3>

<table>
  <thead>
    <tr>
      <th>Directory</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/home</td>
      <td>Default location for user home directories.</td>
    </tr>
    <tr>
      <td>/opt</td>
      <td>Used for installing optional third-party software.</td>
    </tr>
    <tr>
      <td>/srv</td>
      <td>Holds data for services like web servers (rarely used in containers).</td>
    </tr>
    <tr>
      <td>/root</td>
      <td>Home directory for the root user.</td>
    </tr>
  </tbody>
</table>

<h3>Temporary &amp; Volatile Directories</h3>

<table>
  <thead>
    <tr>
      <th>Directory</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/tmp</td>
      <td>Temporary files (cleared on reboot).</td>
    </tr>
    <tr>
      <td>/run</td>
      <td>Holds runtime data for processes.</td>
    </tr>
    <tr>
      <td>/proc</td>
      <td>Virtual filesystem for process and system information.</td>
    </tr>
    <tr>
      <td>/sys</td>
      <td>Virtual filesystem for hardware and kernel information.</td>
    </tr>
    <tr>
      <td>/dev</td>
      <td>Contains device files (e.g., /dev/null, /dev/sda).</td>
    </tr>
  </tbody>
</table>

<h3>Mount Points</h3>

<table>
  <thead>
    <tr>
      <th>Directory</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>/mnt</td>
      <td>Temporary mount point for external filesystems.</td>
    </tr>
    <tr>
      <td>/media</td>
      <td>Mount point for removable media (USB, CDs).</td>
    </tr>
    <tr>
      <td>/data</td>
      <td>Likely your mounted volume from Windows (C:/ubuntu-data).</td>
    </tr>
  </tbody>
</table>

