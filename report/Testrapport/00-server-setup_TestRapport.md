# Enterprise Linux Lab Report

- Student name:Tom Stechele
- Github repo: <https://github.com/tomstechele/elnx-sme-tomstechele>

Describe the goals of the current iteration/assignment in a short sentence.




## Test rapport

Every lab report should contain a test plan. To give an idea of what is meant by this, a test plan for this assignment is given here.

- On the host system, go to the local working directory of the project repository
- Execute `vagrant status`
    - There should be one VM, `pu004` with status `not created`. If the VM does exist, destroy it first with `vagrant destroy -f pu004`


- Execute `vagrant up pu004`
    - The command should run without errors (exit status 0)

   ![vagrant up pu004](https://github.com/tomstechele/elnx-sme-tomstechele/blob/tomstechele/report/Images/00-server-setup/vagrant_up.PNG)




- Log in on the server with `vagrant ssh pu004` and run the acceptance tests. They should succeed

 ![vagrant ssh pu004](https://github.com/tomstechele/elnx-sme-tomstechele/blob/tomstechele/report/Images/00-server-setup/vagrant_ssh.PNG)

    ```
    [vagrant@pu004 test]$ sudo /vagrant/test/runbats.sh
    Running test /vagrant/test/common.bats
    ✓ EPEL repository should be available
    ✓ Bash-completion should have been installed
    ✓ bind-utils should have been installed
    ✓ Git should have been installed
    ✓ Nano should have been installed
    ✓ Tree should have been installed
    ✓ Vim-enhanced should have been installed
    ✓ Wget should have been installed
    ✓ Admin user bert should exist
    ✓ Custom /etc/motd should be installed

    10 tests, 0 failures
    ```
![vagrant test slagen](https://github.com/tomstechele/elnx-sme-tomstechele/blob/tomstechele/report/Images/00-server-setup/vagrant_test.PNG)

    Any tests for the LAMP stack may fail, but this is not part of the current assignment.

5. Log off from the server and ssh to the VM as described below. You should **not** get a password prompt.

    ```
    $ ssh bert@192.0.2.50
    Welcome to pu004.localdomain.
    enp0s3     : 10.0.2.15         fe80::a00:27ff:fe5c:6428/64
    enp0s8     : 192.0.2.50        fe80::a00:27ff:fecd:aeed/64
    [bert@pu004 ~]$
    ```