<h2>VI Editor Shortcuts</h2>

<h3>Modes in VI Editor</h3>
<ul>
  <li><strong>Normal Mode (default)</strong> – Used for navigation and command execution.</li>
  <li><strong>Insert Mode</strong> – Used for text editing (press <code>i</code> to enter, <code>Esc</code> to exit).</li>
  <li><strong>Command Mode</strong> – Used for saving, quitting, and searching (press <code>:</code> in Normal mode).</li>
</ul>

<h3>Basic Navigation</h3>
<table>
  <thead>
    <tr>
      <th>Shortcut</th>
      <th>Action</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>h</td><td>Move left</td></tr>
    <tr><td>l</td><td>Move right</td></tr>
    <tr><td>j</td><td>Move down</td></tr>
    <tr><td>k</td><td>Move up</td></tr>
    <tr><td>0</td><td>Move to the beginning of the line</td></tr>
    <tr><td>^</td><td>Move to the first non-blank character of the line</td></tr>
    <tr><td>$</td><td>Move to the end of the line</td></tr>
    <tr><td>w</td><td>Move to the next word</td></tr>
    <tr><td>b</td><td>Move to the previous word</td></tr>
    <tr><td>gg</td><td>Move to the start of the file</td></tr>
    <tr><td>G</td><td>Move to the end of the file</td></tr>
    <tr><td>:n</td><td>Move to line number <em>n</em></td></tr>
  </tbody>
</table>

<h3>Insert Mode Shortcuts</h3>
<table>
  <thead>
    <tr>
      <th>Shortcut</th>
      <th>Action</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>i</td><td>Insert before cursor</td></tr>
    <tr><td>I</td><td>Insert at the beginning of the line</td></tr>
    <tr><td>a</td><td>Append after cursor</td></tr>
    <tr><td>A</td><td>Append at the end of the line</td></tr>
    <tr><td>o</td><td>Open a new line below</td></tr>
    <tr><td>O</td><td>Open a new line above</td></tr>
    <tr><td>Esc</td><td>Exit insert mode</td></tr>
  </tbody>
</table>

<h3>Editing Text</h3>
<table>
  <thead>
    <tr>
      <th>Shortcut</th>
      <th>Action</th>
    </tr>
  </thead>
  <tbody>
    <tr><td>x</td><td>Delete a character</td></tr>
    <tr><td>X</td><td>Delete a character before cursor</td></tr>
    <tr><td>dw</td><td>Delete a word</td></tr>
    <tr><td>dd</td><td>Delete a line</td></tr>
    <tr><td>d$</td><td>Delete from cursor to end of line</td></tr>
    <tr><td>d0</td><td>Delete from cursor to beginning of line</td></tr>
    <tr><td>D</td><td>Delete from cursor to end of line</td></tr>
    <tr><td>u</td><td>Undo last action</td></tr>
    <tr><td>Ctrl + r</td><td>Redo an undone change</td></tr>
    <tr><td>yy</td><td>Copy (yank) a line</td></tr>
    <tr><td>yw</td><td>Copy (yank) a word</td></tr>
    <tr><td>p</td><td>Paste after the cursor</td></tr>
    <tr><td>P</td><td>Paste before the cursor</td></tr>
  </tbody>
</table>

<h3>Search and Replace</h3>
<pre><code>/pattern            # Search forward for a pattern
?pattern            # Search backward for a pattern
n                   # Repeat last search forward
N                   # Repeat last search backward
:%s/old/new/g       # Replace all occurrences in the file
:s/old/new/g        # Replace all occurrences in the current line
</code></pre>

<h3>Working with Multiple Files</h3>
<pre><code>:e filename         # Open a new file
:w                  # Save file
:wq                 # Save and exit
:q!                 # Quit without saving
:split filename     # Split screen horizontally
:vsplit filename    # Split screen vertically
Ctrl + w + w        # Switch between split screens
</code></pre>
