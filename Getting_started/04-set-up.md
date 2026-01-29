<h2>Setup Linux Environment on Windows and macOS</h2>

<p>
There are multiple ways to set up a Linux environment on Windows or macOS machines such as
cloud VMs, WSL2, VirtualBox, HyperKit, etc. However, a highly recommended and lightweight
approach is using <strong>containers</strong> as a Linux environment.
</p>

<p>
By installing <strong>Docker Desktop</strong>, you can quickly spin up a Linux container of any
distribution without worrying about cost or connectivity issues.
</p>

<h3>Docker Command to Run Ubuntu Linux Container on Windows Host (Persistent &amp; Long-Term)</h3>

<p>
Create a folder named <code>ubuntu-data</code> inside your <code>Downloads</code> directory.
Then run the following command in <strong>PowerShell</strong> (update the username accordingly).
</p>

<pre><code>docker run -dit `
  --name ubuntu-container `
  --hostname ubuntu-dev `
  --restart unless-stopped `
  --cpus="2" `
  --memory="4g" `
  --mount type=bind,source="C:/Users/Monica Korla/Downloads/ubuntu-container",target=/data `
  -v /var/run/docker.sock:/var/run/docker.sock `
  -p 2222:22 `
  -p 8080:80 `
  --env TZ=Asia/Kolkata `
  --env LANG=en_US.UTF-8 `
  ubuntu:latest /bin/bash
</code></pre>

<h3>Docker Command to Run Ubuntu Linux Container on macOS or Linux Host (Persistent &amp; Long-Term)</h3>

<pre><code>docker run -dit \
  --name ubuntu-container \
  --hostname ubuntu-dev \
  --restart unless-stopped \
  --cpus="2" \
  --memory="4g" \
  --mount type=bind,source=/tmp/ubuntu-data,target=/data \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -p 2222:22 \
  -p 8080:80 \
  --env TZ=Asia/Kolkata \
  --env LANG=en_US.UTF-8 \
  ubuntu:latest /bin/bash
</code></pre>

<h3>Explanation of Each Parameter</h3>

<table>
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>-dit</td>
      <td>Runs the container in detached (-d), interactive (-i), and terminal (-t) mode.</td>
    </tr>
    <tr>
      <td>--name ubuntu-container</td>
      <td>Assigns a name to the container for easy management.</td>
    </tr>
    <tr>
      <td>--hostname ubuntu-dev</td>
      <td>Sets the container’s hostname.</td>
    </tr>
    <tr>
      <td>--restart unless-stopped</td>
      <td>Automatically restarts the container unless it is manually stopped.</td>
    </tr>
    <tr>
      <td>--cpus="2"</td>
      <td>Limits the container to use 2 CPU cores.</td>
    </tr>
    <tr>
      <td>--memory="4g"</td>
      <td>Allocates 4GB of RAM to the container.</td>
    </tr>
    <tr>
      <td>--mount type=bind,source=...,target=/data</td>
      <td>Mounts a host directory into the container to persist data.</td>
    </tr>
    <tr>
      <td>-v /var/run/docker.sock:/var/run/docker.sock</td>
      <td>Allows running Docker commands inside the container (optional).</td>
    </tr>
    <tr>
      <td>-p 2222:22</td>
      <td>Maps host port 2222 to container port 22 (SSH access).</td>
    </tr>
    <tr>
      <td>-p 8080:80</td>
      <td>Maps host port 8080 to container port 80 (web services).</td>
    </tr>
    <tr>
      <td>--env TZ=Asia/Kolkata</td>
      <td>Sets the timezone inside the container.</td>
    </tr>
    <tr>
      <td>--env LANG=en_US.UTF-8</td>
      <td>Sets the language and locale configuration.</td>
    </tr>
    <tr>
      <td>ubuntu:latest /bin/bash</td>
      <td>Uses the latest Ubuntu image and starts a Bash shell.</td>
    </tr>
  </tbody>
</table>
