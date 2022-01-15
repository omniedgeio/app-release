# OmniEdge Linux CLi

## Installing on Linux

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
![omniedge cli ](../OmniEdge-CLI-0.2.0.gif)

## Release Notes

|Version|Release Date|Notes|
|---|---|---|
|v0.2.3 |August,30, 2021|Optimize workflow|
|v0.2.2  |August,3, 2021|Fix incorrect device mac block the OmniEdge start|
|v0.2.1 |August,2, 2021|Initial release , new backend API|
|v0.1.0|Apr 8, 2021|Initial release|


-----

If you have more questions, feel free to [contact us](mailto:support@omniedge.io).