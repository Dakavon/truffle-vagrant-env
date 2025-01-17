# VM for Ethereum smart contract development
on the basis of Ubuntu 22.04 LTS ("Jammy Jellyfish") with pre-installed software e.g. Truffle ~+ Hardhat~ (\*) to get started straight away.

(\* Hardhat needs a local installation within a project.)

See [bootstrap.sh](bootstrap.sh) for software versions.

## Get started
### Download and install Vagrant for your system
:arrow_right: https://www.vagrantup.com/downloads
### Download and install Virtualbox for your system (because Vagrant relies on "providers")
:arrow_right: https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html (or https://download.virtualbox.org/virtualbox)

        $ sudo dpkg -i virtualbox-_VERSION_~Ubuntu~_PLATFORM.deb
        $ sudo apt-get install --fix-broken install


### Prepare development environment

1. Clone this repo
    ```sh
    $ git clone git@github.com:Dakavon/truffle-hardhat-vagrant-env.git
    ```

2. Go into the download folder and prepare development environment with
    ```sh
    $ cd truffle-hardhat-vagrant-env
    $ vagrant up
    ```

3. [Wait](https://www.youtube.com/watch?v=VBlFHuCzPgY) until it is finished :)

4. The Vagrant VM is now running. To shut it down, you can enter the following:
    ```sh
    $ vagrant halt
    ```


### Run development environment

1. If you haven't already create a DAPPS folder within your users home folder, e.g. vua terminal
    ```sh
    $ mkdir ~/DAPPS
    ```

2. Open VM installation folder in a terminal

3. Start VM and log in
    ```sh
    $ vagrant up && vagrant ssh
    ```

4. Go to ~DAPPS folder inside the VM
    ```sh
    vagrant@devVM:~$  cd ~/DAPPS/
    ```

5. Clone project from `_REPOSITORY_` to your DAPPS folder (likely from outside the VM due to public-key authentication)
    ```sh
    $ git clone git@github.com:_REPOSITORY_
    ```

6. Go to `_PROJECT_` folder inside the VM and install dependencies via
    ```sh
    vagrant@devVM:~/DAPPS$  cd _PROJECT_ && npm install
    ```

7. Use hardhat within project through local installation
    ```sh
    vagrant@devVM:~/DAPPS/_PROJECT_$   npm install --save-dev hardhat
    ```


### Delete development environment

1. Go to the download folder and delete development environment with
    ```sh
    $ cd truffle-hardhat-vagrant-env
    $ vagrant destroy
    ```