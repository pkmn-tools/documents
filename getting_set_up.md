# Getting set up
This document will show you how to get everything set up to contribute and build the project.

## Instructions
1. Clone the [metarepository](https://github.com/GDChaoticTCG/GDChaoticTCG)

 ```
 GIT_SSH_COMMAND="ssh -i /path/to/your/ssh/privatekey" git clone --recurse-submodules git@github.com:GDChaoticTCG/GDChaoticTCG.git
 ```

 Note: This may prompt you to enter your password multiple times. This is normal, and do not be surprised if it does not show you anything as you type.

2. Configure git to use your private SSH key all the time

 Then you will need to configure the repository and all submodules to use your ssh key as well

 ```
 cd GDChaoticTCG
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 cd Documents
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 cd ../Server
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 cd ../Client
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 ```

