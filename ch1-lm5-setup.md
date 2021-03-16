#### [ GBDS Landmark Update 2021 ] [ Part-1 ]


# Setup Landmark 5

> These instructions outline `Part-1` in the process for `GBDS staff` to update their Linux user accounts to Landmark DSG 10ep4 and start using the new software.


> &#x2217;&#x2217;&#x2217; Don't do `Part-1` alone.<br>
> &emsp; &#x2192; To avoid data-loss, all GBDS users need to complete this step at the same time.

<br>

## &#x2B1C;&#x00A0; step-1 : Set lm5

Connect to the VPN and authenticate using Cisco AnyConnect & the DUO app.

### 1.1 Log into a Linux workstation

### 1.2 Open your `Home` folder

### 1.3 Set file browser to show hidden files : `press ctrl H`

<blockquote>
<table style="width:100%">
<tr>
  <td><img src="./img/ch1/step1/set-lm5-1-browser.png" /></td>
  <td><img src="./img/ch1/step1/set-lm5-2-browser-cshrc.png" /></td>
</tr>
<tr>
  <td><b>Figure 1 : (a)&#x00A0; Before <code>ctrl-H</code></b></td>
  <td><b>(b)&#x00A0; After <code>ctrl-H</code></b></td>
</tr>
</table>
</blockquote>

<br>

### 1.4 Open `.cshrc` with a text-editor (gedit, emacs, etc)

&emsp; &#x2192; Right-click the file & "Open with..."

<blockquote>

| <img src="./img/ch1/step1/set-lm5-3-edit-cshrc.png" /> |
|--------------------------------------------------------|
| Figure 2 : Location of `.cshrc` run-command file       |
</blockquote>

<br>

### 1.5 Edit `.cshrc` as follows:

> * change <code>&#x2003; set LANDMARK4</code> to <code># set LANDMARK4</code>
> * change <code># set LANDMARK5</code> to <code>&#x2003; set LANDMARK5</code>

<blockquote>
<table style="width:100%">
<tr>
  <td><img src="./img/ch1/step1/set-lm5-4-edit-cshrc.png" /></td>
  <td><img src="./img/ch1/step1/set-lm5-5-edit-cshrc.png" /></td>
</tr>
<tr>
  <td><b>Figure 3 : (a)&#x00A0; With <code>LANDMARK4</code>set</b></td>
  <td><b>(b)&#x00A0; With <code>LANDMARK5</code>set</b></td>
</tr>
</table>
</blockquote>

<br>

### 1.6 `ctrl H` again to re-hide hidden files

<br>

## &#x2B1C;&#x00A0; step-2 : Set VNC

### 2.1 Open terminal / command prompt

> * Do this from your home computer, not from a remote desktop

<br>

### 2.2 Connect to the UTIG remote server using `ssh`:
 
```bash
ssh <your-user-name>@ig-<computer-name>.ig.utexas.edu
```
<br>

### 2.3 Enter your unix account password (not eid pw)

> * FYI - The password field stays blank when you type
> * Press `Enter` when done
> * (sometimes takes 20–30 sec to process after password-entry)

<br>

### 2.4 List your acitve `vncserver` sessions:

```bash
vncserver -list
```

```bash
# EXAMPLE OUTPUT #

TurboVNC sessions:

X DISPLAY #  PROCESS ID
:1           16000
:2           4079
```
<br>

### 2.5 Kill acitve `vncserver` sessions:

> * Repeat as needed to kill all sessions
> * Use the display number(s) from step-4 &nbsp;&#x2192;&nbsp; including the `:`


```bash
vncserver -kill :<display-number>

```

<!--
<details>
<summary><b>see video</b></summary>

<video width="70%" controls loop>
<source src="./img/ch1/step2/set-vnc-1-list-kill.mov">
</video>
</details>
-->

<br>

### 2.6 Close UTIG server connection : `press ctrl d`

```bash
# EXAMPLE OUTPUT #

ig-123456.ig.utexas.edu 363% logout
Connection to ig-123456.ig.utexas.edu closed.
➜  ~
```

<br>

### 2.7 Open new terminal window & Connect to UTIG server:

```bash
ssh <your-user-name>@ig-<computer-name>.ig.utexas.edu

<enter password>
```

<br>

### 2.8 Start the VNC server:

```bash
vncserver

```

<br>

### 2.9 Close UTIG server connection : `press ctrl d`

<!--
<details>
<summary><b>see video</b></summary>

<video width="70%" controls loop>
<source src="./img/ch1/step2/set-vnc-2-start.mov">
</video>
</details>
-->

<br>
