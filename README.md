Moved to: https://github.com/omniedgeio/omniedge/releases

# OmniEdge app release

**Notice**: 
By using this server to install OmniEdge, you acknowledge that you have read and accepted [OmniEdge's TOS](https://omniedge.io/terms).

OmniEdge are compatible with the following operating systems:

| Operating Systems  | OS Distribution |
| :---    | :---:   |
| Amazon Linux | [Amazon Linux 2](#-Amazon-Linux-2)  |
| CentOS  | [CentOS 7](#-CentOS-7)  \| [CentOS 8](#-CentOS-8) |
|Debian|[Debian Stretch](#-Debian-Stretch)  \| [Debian Buster](#-Debian-Buster)|
|Fedora|[Fedora](#-Fedora)|
|Raspbian|[Raspbian Buster (for Raspberry Pi)](#-Raspbian-Buster)|
|Ubuntu|[Ubuntu 16.04 LTS (Xenial)](#-Ubuntu-16.04-LTS-(Xenial)) \| [Ubuntu 18.04 LTS (Bionic)](#-Ubuntu-18.04-LTS-(Bionic)) \| [Ubuntu 19.10 (Eoan)](#-Ubuntu-19.10-(Eoan))  \| [Ubuntu 20.04 LTS (Focal)](#-Ubuntu-20.04-LTS-(Focal))  \| [Ubuntu 20.10 (Groovy)](#-Ubuntu-20.10-(Groovy))  \| [Ubuntu 21.04 (Hirsute)](#-Ubuntu-21.04-(Hirsute)) \| [Ubuntu 21.10 (Impish)](#-Ubuntu-21.10-(Impish))|
|Windows |Windows 7 \| Windows 10|
|Android| Android 6 or later|
|MacOS|M1 or Intel Mac with macOS 10 or later|
|iOS|iOS 15.0 or later|

# Installation

Reference: [https://www.omniedge.io/docs/article/Install](https://www.omniedge.io/docs/article/Install)

## 1. Get Started

+ Sign up your account: [Sign up](https://omniedge.io/register)
+ Download OmniEdge with the link: [Download OmniEdge](https://omniedge.io/download)

## 2. Installing on Windows
OmniEdge Windows is compatible with Windows 7,10(arm) & Windows Server 2016,2019. `Last update: Version 0.2.0, January 15,2022.`

[Download OmniEdge Windows for 7 or later](windows/omniedge-setup-0.2.0.exe)

+ Download and run the Windows installer

+ Click on "Log in…" from the Omniedge icon now in your system tray

+ Sign in with your email address

+ Click "Connect" in the menu bar from the tray icon. After a pop-up disappears, a secure VPN connection is initialized.

## 3. Installing on MacOS

OmniEdge MacOS Cli is compatible with intel Macbook, macOS 10 or later Last update: Version 0.2.0, January 15, 2022.

*To use OmniEdge on MacOS, please instal Tun/Tap Driver first*

### 3.1 Install Tun/Tap Driver:

#### For Intel Mac: 

  - Download tuntap driver from [https://sourceforge.net/projects/tuntaposx/files/latest/download](https://sourceforge.net/projects/tuntaposx/files/latest/download) 
  - Extract `tuntap_20150118.tar.gz` and Install tuntap by running **tuntap_20150118.pkg**

#### For M1 Mac user: 

  - Download `https://github.com/Tunnelblick/Tunnelblick/tree/master/third_party/tap-notarized.kext`
  - Download `https://github.com/Tunnelblick/Tunnelblick/tree/master/third_party/tun-notarized.kext`
  - Change the name to **tap.kext** and **tap.kext**, 
  - Copy to **/Library/Extensions**
  - add `net.tunnelblick.tap.plist` and `net.tunnelblick.tun.plist` to `/Library/LaunchDaemons/`

  ```bash
    #net.tunnelblick.tap.plist
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>net.tunnelblick.tap</string>
        <key>ProgramArguments</key>
        <array>
            <string>/sbin/kextload</string>
            <string>/Library/Extensions/tap.kext</string>
        </array>
        <key>KeepAlive</key>
        <false/>
        <key>RunAtLoad</key>
        <true/>
        <key>UserName</key>
        <string>root</string>
    </dict>
    </plist>

  ```

  ```bash
    #net.tunnelblick.tun.plist
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>net.tunnelblick.tun</string>
        <key>ProgramArguments</key>
        <array>
            <string>/sbin/kextload</string>
            <string>/Library/Extensions/tun.kext</string>
        </array>
        <key>KeepAlive</key>
        <false/>
        <key>RunAtLoad</key>
        <true/>
        <key>UserName</key>
        <string>root</string>
    </dict>
    </plist>
  ```
- restart Mac after allowing the security check. 


### 3.2 Use OmniEdge cli on MacOS

+ Sign up your account: [Sign up](https://omniedge.io/register)

+ Download and install omnidge cli by running the following command:

``` bash
curl https://omniedge.io/install/omniedge-install.sh | bash
```

+ Login By Password:

``` bash
omniedge login -u yourname@youremail.com -f your_auth_file_path
```
+ Login By Secret-Key, You can generate secret-key on omniedge web

```bash
omniedge login -s yoursecuritykey -f your_auth_file_path
```

+ Join Your Network,you can just call omniedge join, it will automatically prompt the available network for you to choose. And you can also add one parameter -n to specify the network id manually. And then, enjoy the omniedge network.

```bash
sudo omniedge join -f your_auth_file_path
```
and select your virtual network or

``` bash
sudo omniedge join -n 'virtual-network-id'
```
with a speicified virtual network.

+ Wait a second and a secure VPN will be established
![](OmniEdge-CLI-0.2.0.gif)

## 4. Installing on Android

OmniEdge Android is compatible with Android 6 or later mobile phone or TV. Last update: Version 0.2.0, January 15,2022.

[Download for Android 6 or later](android/omniedge-android-0.2.0.apk)

+ Download OmniEdge APK and install it
+ Run OmniEdge and Sign in with your email address
+ Click the connect button
+ Allow installing a VPN configuration
+ Enjoy the secure VPN connection

## 5. Installing on Linux

OmniEdge Linux Cli is Compatible with linux for AMD64,Apple M1, Intel X86, ArmV7 and Arm64V8, Last update: Version 0.2.0, January 15, 2022.

+ Sign up your account: [Sign up](https://omniedge.io/register)

+ Download and install omnidge cli by running the following command:

``` bash
curl https://omniedge.io/install/omniedge-install.sh | bash
```

+ Login By Password:

``` bash
omniedge login -u yourname@youremail.com -f your_auth_file_path
```
+ Login By Secret-Key, You can generate secret-key on omniedge web

```bash
omniedge login -s yoursecuritykey -f your_auth_file_path
```

+ Join Your Network,you can just call omniedge join, it will automatically prompt the available network for you to choose. And you can also add one parameter -n to specify the network id manually. And then, enjoy the omniedge network.

```bash
sudo omniedge join -f your_auth_file_path
```
and select your virtual network or

``` bash
sudo omniedge join -n 'virtual-network-id'
```
with a speicified virtual network.

+ Wait a second and a secure VPN will be established
![omniedge cli ](OmniEdge-CLI-0.2.0.gif)

## Run OmniEdge as a Service

+ After login in omniedge, run the command `omniedge join -f .omniedge/auth.json` to get your virutal network ID.

```bash
omniedge join -f .omniedge/auth.json

INFO[0000] You are in mode: prod
INFO[2022-01-17T11:34:28] List Virtual Network response
Use the arrow keys to navigate: ↓ ↑ → ←  and / toggles search
choose the network
  🌶 Home

--------- Virtual Network ----------
Name:        Home
Cidr:        100.100.0.0/24
Role:        2
ID:          your_virtual_network_id

```

+ Change the virtual network and your_auth_file_path in **omniedge.service**

```bash
[Unit]
Description=omniedge process
After=network-online.target syslog.target nfw.target
Wants=network-online.target

[Service]
Type=simple
ExecStartPre=
#Replace to your real virtual network id(can be found by run omniedge join) and auth.json path
ExecStart=/usr/local/bin/omniedge join -n "your_virtual_network_id" -f your_auth_file_path
Restart=on-abnormal
RestartSec=5

[Install]
WantedBy=multi-user.target
Alias=

```

+ Copy `omniedge.service`

```bash
cp linux/etc/systemd/system/omniedge.service /etc/systemd/system/
```

+ Activate `omniedge.service`

```bash
systemctl daemon-reload
systemctl enable omniedge.service
systemctl enable omniedge.service
```


## 6. Installing on iOS

[https://apps.apple.com/us/app/omniedgenew/id1603005893](https://apps.apple.com/us/app/omniedgenew/id1603005893)

<img width="149" alt="Screen Shot 2022-06-22 at 10 11 07 PM" src="https://user-images.githubusercontent.com/93888/175051476-eb94cea3-1f38-42da-87b4-ab387652dd0d.png">



-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).
