# OmniEdge macOS Cli

## Installing on MacOS

OmniEdge MacOS Cli is compatible with intel Macbook, macOS 10 or later Last update: Version 0.2.3, April, 25,2022

*To use OmniEdge on MacOS, please instal Tun/Tap Driver first*

### Install Tun/Tap Driver:

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


### Use OmniEdge cli on MacOS

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
![](../OmniEdge-CLI-0.2.0.gif)

## Release Notes

|Version|Release Date|Notes|
|--|--|--|
|0.2.3|April, 25, 2022|Add refresh token|
|0.2.2|February, 27,2022|Fix machine ID error|
|0.2.1|January, 15, 2022|Integrated with new backend|
|0.2.0 |August,2, 2021|Initial release , new backend API,Optimize workflow,Fix incorrect device mac block the OmniEdge start|
|0.1.0|Apr 8, 2021|Initial release|

-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).