# how to set up dev environment for new hires

## WSL

### Prerequisites

- set up access to AWS SSO in appropriate accounts
- create github account in Retail-Success organization

### Getting started

1. Install WSL
    1. enable through control panel # TODO THIS NEEDS MORE IN DEPTH GUIDANCE
2. Install Ubuntu
    1. go to Windows store and search for `ubuntu 20.04 lts`
    2. click `install`
    3. click `launch`
3. Install Windows Terminal
    1. go to Windows store and search for `Terminal`
    2. click `install`
    3. click `launch`
4. Open terminal
    1. click windows
    2. click the down arrow next to the `+` (where the second "tab" would be)
    3. select ubuntu
4. Update your installation
   1. run `sudo apt-get udpate && sudo apt-get upgrade -y`
5. Install Visual Studio code
    1. navigate here https://code.visualstudio.com/ and follow necessary steps to install
6. Install necessary packages
    1. Install necessary apt packages with the following command
    ```
    sudo apt-get install zsh curl jq git unzip wget zip python3 python3-pip
    ```
    2. Install aws command line tools
    ```
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && unzip awscliv2.zip && ./aws/install
    ```
7. start using zsh with
    ```
    chsh -s $(which zsh)
    sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
8. install terraform (replace <TERRAFORMVERSION> with the latest release of terraform which can be found here https://www.terraform.io/downloads.html)
    ```
    wget https://releases.hashicorp.com/terraform/<TERRAFORMVERSION>/terraform_<TERRAFORMVERSION>_linux_amd64.zip && \
    unzip terraform_<TERRAFORMVERSION>_linux_amd64.zip -d /usr/bin
    ```
9. go get your aws keys
    navigate to `https://retailsuccesscloud.awsapps.com/start#/` in your browser
    1. sign in using
        username: `cloud/YOURUSERNAME`
        password: `YOURPASSSWORD`
    2. after signing in, click the box with `AWS Account (x)`
    3. select the account you want
    4. click "Command line or programatic access"
    5. copy the text from option 2
    6. paste the file into `~/.aws/credentials`
    7. change the top line to say `[default]`
    7. run `aws sts get-caller-identity` to verify AWS access

