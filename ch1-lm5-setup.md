#### [ GBDS Landmark Update 2021 ] [ Part-1 ]


# Setup Landmark 5

> These instructions outline `Part-1` in the process for `GBDS staff` to update their Linux user accounts to Landmark DSG 10ep4 and start using the new software.


> &#x2217;&#x2217;&#x2217; Don't do `Part-1` alone.<br>
> &emsp; &#x2192; To avoid data-loss, all GBDS users need to complete this step at the same time.


<details>
<summary style="font-size:1.0em">Background</summary>

### Deployed

>
![Linux](https://img.shields.io/badge/platform-rhel%206*%20|%20rhel%207-orange?style=flat-square&logo=red-hat)
![OpenWorks](https://img.shields.io/badge/OpenWorks-5000.10.6.0-419B59?style=flat-square)
![DecisionSpace](https://img.shields.io/badge/DecisionSpace-10ep.4.03-8FC965?style=flat-square)
<br><sup>&#xFF0A; rhel 6 is being phased out, but is still available in limited capacity


### Deprecated

> **Maintenance has expired for these applications, and they're no longer UT ISO no longer supports them:**

> * DecisionSpace 10ep.0.05
> * OpenWorks 5000.10.2.0
> * Red Hat Enterprise Linux v6 (in-progress)

### Shorthand + Abbreviations

>
<table style="width:100%">
  <tr>
    <td><b>DSG</b></td>
    <td>DecisionSpace Geoscience <br><sub>i.e. DecisionSpace (at some point Landmark added "Geoscience" to the name)</sub></td>
  </tr>
  <tr>
    <td><b>lm4, lm5</b></td>
    <td>Landmark4 & Landmark5 <br><sub> 	&#x2192; UTIG's internal naming convention for the deprecated & new versions, respectively</sub></td>
  </tr>
  <tr>
    <td><b>10ep.x.xx</b></td>
    <td>DecisionSpace version number</td>
  </tr>
  <tr>
    <td><b>10ep</b></td>
    <td>the version being deprecated (10ep.0.05) <br><sub>i.e. "Landmark4" , "lm4"</sub></td>
  </tr>
  <tr>
    <td><b>10ep4</b></td>
    <td>the version being deployed (10ep.4.03) <br><sub>i.e. "Landmark5" , "lm5"</sub></td></td>
   </tr>
</table>

</details>


## &#x2B1C;&#x00A0; step-1 : Set lm5

Connect to the VPN and authenticate using Cisco AnyConnect & the DUO app.

### 1. Log into a Linux workstation

### 2. Open your `Home` folder

### 3. Set file browser to show hidden files : `press ctrl H`

<blockquote>
<table style="width:100%">
<tr>
  <td><img src="./img/ch1/step1/set-lm5-1-browser.png" /></td>
  <td><img src="./img/ch1/step1/set-lm5-2-browser-cshrc.png" /></td>
</tr>
<tr>
  <td><b>Fig. 1.1 : Before <code>ctrl-H</code></b></td>
  <td><b>Fig. 1.2 : After <code>ctrl-H</code></b></td>
</tr>
</table>
</blockquote>

<br>

### 4. Open `.cshrc` with a text-editor (gedit, emacs, etc)

&emsp; &#x2192; Right-click the file & "Open with..."

<blockquote>

| <img src="./img/ch1/step1/set-lm5-3-edit-cshrc.png" /> |
|--------------------------------------------------------|
| Figure 2 : Location of `.cshrc` run-command file       |
</blockquote>

<br>

### 5. Edit `.cshrc` as follows:

> * change <code>&#x2003; set LANDMARK4</code> to <code># set LANDMARK4</code>
> * change <code># set LANDMARK5</code> to <code>&#x2003; set LANDMARK5</code>

<blockquote>
<table style="width:100%">
<tr>
  <td><img src="./img/ch1/step1/set-lm5-4-edit-cshrc.png" /></td>
  <td><img src="./img/ch1/step1/set-lm5-5-edit-cshrc.png" /></td>
</tr>
<tr>
  <td><b>Fig 3.1 : With <code>LANDMARK4</code>set</b></td>
  <td><b>Fig 3.2 : With <code>LANDMARK5</code>set</b></td>
</tr>
</table>
</blockquote>

<br>

### 6. `ctrl H` again to re-hide hidden files

<br>

## &#x2B1C;&#x00A0; step-2 : Set VNC

### 1. Open terminal / command prompt

### 2. Connect to the remote server using `ssh`:
 
```bash
ssh <your-user-name>@ig-<computer-name>.ig.utexas.edu
```
<br>

### 3. Enter your account password (not eid pw)

> * FYI - The password field stays blank when you type
> * Press `Enter` when done
> * (sometimes takes 20–30 sec to process after password-entry)

### 4. List your acitve `vncserver` sessions:

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

### 5. Kill acitve sessions & Close server connection:

<details>
<summary><b>see video</b></summary>

<video width="70%" controls loop>
<source src="./img/ch1/step2/set-vnc-1-list-kill.mov">
</video>
</details>

```bash
# REPEAT AS NEEDED TO KILL ALL SESSIONS #

vncserver -kill :<display-number>
```
```bash
# CLOSE CONNECTION #

exit
```

<br>

### 6. Open new terminal window & Connect to server:

```bash
ssh <your-user-name>@ig-<computer-name>.ig.utexas.edu

<enter password>
```

<br>

### 7. Start the VNC server & Exit:

<details>
<summary><b>see video</b></summary>

<video width="70%" controls loop>
<source src="./img/ch1/step2/set-vnc-2-start.mov">
</video>
</details>

```bash
vncserver
exit
```
