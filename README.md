> [TOC]

# ALM: 

### I. [Pulse Secure](/JVyXq8Z8RT2Rya42nHLH3Q) Connection

Before connecting to remote computer, we need **Pulse Secure**:
1)  Open pulse Secure
2)  Look for Microfocus Uk 
3)  Then check SMS OTP for autithencation
4)  Check Save settings
5)  Type the OTP into the Pulse Secure software
![](https://s2.gifyu.com/images/2021-01-19-16.00.21.gif)


### II. Remote Desktop

Step 1: Install remote desktop from [microsoft store](https://www.microsoft.com/en-us/p/microsoft-remote-desktop/9wzdncrfj3ps?rtc=1&activetab=pivot:overviewtab)

Step 2: Add remote hostby IP.
** Windows Naming Convention: Windows 2016 WIN_0001
![](https://i.imgur.com/uqsgrQj.gif)

### III. Install ALM machine:

#### A. Preparation for installation

>                   1. Adding proxy to Internet Explorer:
![](https://i.imgur.com/p9Hjqwl.gif)
 ```
* Internet  Options -> Connections -> Lan Settings -> Check Use a Proxy server for your LAN:
* Address:   web-proxy.in.softwaregrp.net
* Port:   8080
```
2. Mapping Shared Folder at this ip address //15.226.164.180
3. Install Java runtime environment [here](https://dsh.re/36dd1d).
>        4. Extract ALM windows from the mapped network drive
![](https://i.imgur.com/XkVfVxY.gif)

5. Turn off Firewall.
>              6. Turn off IE server management 
![](https://i.imgur.com/fTzLjWx.gif)



#### B. Configuring Database Server

- Add a [database on mysql](https://dsh.re/7379e) 
- Add a virtual machine to Remote Desktop. Check https://dsh.re/5b69b for configuration detail.
```
PC name: 15.226.164.63
User account: Administrator
Display name: SQL Server 2016
```
- Map Shared Folder: \\15.226.164.180\Share180. Install the following Softwares:

#### C. Installing SQL Services:
- Go to software Install, choose the **SQL Service Installation Center**:
`Z:\Software Installer\DB Installer`
![](https://i.imgur.com/Mzv1URp.gif)
- Enter the Super Admin (SA) password:
![](https://i.imgur.com/WrYlsVi.gif)


#### D. Configuring Microsoft SQL Server Management Studio (Administrator)

![](https://i.imgur.com/2vo789B.gif)
  `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Microsoft SQL Server Tools 18`
- Create a new Logins under localhost -> Security -> Logins. Choose SQL Server autithencation. Uncheck all enforce checkboxes. 
- Click Server roles, and assign dbcreator, public, securityadmin
![](https://i.imgur.com/2WNh36F.gif)

#### E. Install ALM
-  Add the database to ALM configuration. 
```
[servername]: computer name
[port]: the default port 1433
[jdbc](/xL_d8521S6mlqqYaQuDukA)
schema pass: tdtdtd
Communication Security: Abcde@123456
Site Admin: almadmin
Service (leave blank)
```
![](https://i.imgur.com/kbbhcDL.gif)


[jdbc](/xL_d8521S6mlqqYaQuDukA)

