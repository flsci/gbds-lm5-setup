#### [ GBDS Landmark Update 2021 ] [ Guide-1 : Setup LM5 ]


## step-2:&#x00A0; Reset VNC


### 2.0&#x00A0; Open `Terminal` or `Command-Prompt` from your home computer

### 2.1&#x00A0; Connect to the UTIG remote server using `ssh`:
 
```bash
ssh <your-user-name>@ig-<computer-name>.ig.utexas.edu

```

### 2.2&#x00A0; Enter your unix account password (not eid pw)

> * The password field stays blank when you type
> * Press `enter` when done
> * Sometimes takes 20–30 sec to process after password-entry

### 2.3&#x00A0; List your acitve `vncserver` sessions:

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

### 2.4&#x00A0; Kill `vncserver` sessions:

> * Repeat as needed to kill all sessions
> * Use the display number(s) from previous step (2.3) &nbsp;&#x2192;&nbsp; including the `:`
> * &#x2217;&#x2217;&#x2217; If connected to multiple computers, do this for all of them &#x2217;&#x2217;&#x2217;  

```bash
vncserver -kill :<display-number>

```

### 2.5&#x00A0; Close UTIG server connection : `press ctrl d`

> * Or type `logout` and press `enter`
> * Then type `exit` to close the terminal session
> * Open a fresh terminal window for later

```bash
# EXAMPLE OUTPUT #

ig-123456.ig.utexas.edu 363% logout
Connection to ig-123456.ig.utexas.edu closed.
➜  ~

```

<blockquote>
<details><summary><b>[video] Watch steps 2.0–2.5</b></summary>

![](./img/guide1/step2/set-vnc-1-kill.gif)

</details>
</blockquote>

### 2.6&#x00A0; Open new terminal window & Connect to UTIG server:

```bash
ssh <your-user-name>@ig-<computer-name>.ig.utexas.edu

```

### 2.7&#x00A0; Start the VNC server:

```bash
vncserver

```

### 2.8&#x00A0; Close UTIG server connection : `press ctrl d`

> * Or type `logout` and press `enter`
> * Then type `exit` to close the terminal window
> * Quit the terminal application

<blockquote>
<details><summary><b>[video] Watch steps 2.6–2.8</b></summary>

![](./img/guide1/step2/set-vnc-2-fresh.gif)

</details>
</blockquote>


### 2.9&#x00A0; [Go to Step-3](/step3-verify-lm5.md)

<br>
