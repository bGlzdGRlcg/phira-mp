# phira-mp

`phira-mp` is a project developed with Rust. Below are the steps to deploy and run this project.

[简体中文](README.zh-CN.md) | English Version

## Environment

- Rust 1.70 or later

## Server Installation

### For Linux

#### Dependent
First, install Rust if you haven't already. You can do so by following the instructions at https://www.rust-lang.org/tools/install

For Ubuntu or Debian users, use the following command to install `curl` if it isn't installed yet:

```shell
sudo apt install curl
```
For Fedora or CentOS users, use the following command:
```shell
sudo yum install curl
```
After curl is installed, install Rust with the following command:
```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
Then, build the project:
```shell
cargo build --release -p phira-mp-server
```
#### unning the Server
You can run the application with the following command:
```shell
RUST_LOG=info target/release/phira-mp-server
```

The port can also be specified via parameters:
```shell
RUST_LOG=info target/release/phira-mp-server --port 8080
```

#### Troubleshooting
If you encounter issues related to openssl, ensure that you have libssl-dev (for Ubuntu or Debian) or openssl-devel (for Fedora or CentOS) installed. If the issue persists, you can set the OPENSSL_DIR environment variable for the compilation process.

If you're compiling on Linux and targeting Linux and get a message about pkg-config being missing, you may need to install it:

```shell
# For Ubuntu or Debian
sudo apt install pkg-config libssl-dev 

# For Fedora or CentOS
sudo dnf install pkg-config openssl-devel
```
For other issues, please refer to the specific error messages and adjust your environment accordingly.

#### Monitoring
You can check the running process and the port it's listening on with:
```shell
ps -aux | grep phira-mp-server
netstat -tuln | grep 12345
```
![image](https://github.com/okatu-loli/phira-mp/assets/53247097/b533aee7-03c2-4920-aae9-a0b9e70ed576)

## For Windows or Android
View: [https://docs.qq.com/doc/DU1dlekx3U096REdD](https://docs.qq.com/doc/DU1dlekx3U096REdD)

# listder build
OS:Debian 11
## for amd
```shell
wget https://github.com/bGlzdGRlcg/phira-mp/releases/download/linux/phira_amd
chmod 777 phira_amd
RUST_LOG=debug ./phira_amd --port 8443
```
## for arm
```shell
wget https://github.com/bGlzdGRlcg/phira-mp/releases/download/linux/phira_arm
chmod 777 phira_arm
RUST_LOG=debug ./phira_arm --port 8443
```