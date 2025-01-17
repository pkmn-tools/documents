# Getting set up
This document will show you how to get everything set up to contribute and build the project.

## Setting up a GitHub account and requesting access to the organization
1. If you have not yet signed up for a GitHub account, you will need to do so. Simply visit [the signup page](https://github.com/signup) and sign up for an account.
2. Submit a new issue with the "access" label and sit tight. If I do not respond within a 48 hours, please hit me up on Discord (username brainard50#3809)
3. Since this project relies on git to track source code changes, you will need to be familiar with git. There are many resources available for learning how to use git, but I really like [Git Good](https://www.youtube.com/playlist?list=PLlcnQQJK8SUjuzpRx0U-VEUzhmJD7vGbO)

## Installing Git
### Windows
Download and install the 64-bit Windows installer from [git-scm.com](https://git-scm.com/download/win). You will end up with a shortcut to a program called "git bash" which will be a terminal that allows you to interact with the git cli. It will also grant you access to all of the other tools necessary for managing a git repository.

### macOS
Install through [homebrew](https://brew.sh/). You will need to install homebrew if you have not already.

To install through homebrew, run `brew install git` in the terminal

### Linux
Follow the instructions on [git-scm.com](https://git-scm.com/download/linux) on installing Git for Linux.

## Setting up your GitHub account to use SSH

### Generating an SSH key
In the past, GitHub relied on the username and password to your GitHub account to authenticate you when submitting changes to a repository. Now it authenticates you via SSH key. In order to create an SSH key, you will need to perform the following steps from a terminal (or git bash if you're on Windows)

`ssh-keygen -t ed25519 -C "your_email@example.com"`

When prompted for a file path, you can hit enter to accept the default path and filename. If you want to save it to a different location or use a different filename, you can do that now. I recommend saving it in the same folder it defaults to, but choose a name specific to your github account.

When prompted for a passphrase, I strongly recommend providing a unique and complicated passphrase. If your key gets compromised and bad things happen to the organization, I will promptly remove you from the organization and you may not be allowed to contribute in the future. You can store the passphrase in something like [KeePassXC](https://keepassxc.org/) (this is what I use for all of my password management)

When this process is complete, you will have two files. For example, if you leave the default file names and paths you will have id\_rsa and id\_rsa.pub.

### Adding your public SSH key to GitHub
Navigate to [SSH and GPG keys](https://github.com/settings/keys) within your GitHub settings and click "New SSH Key". You can add a title and then paste the contents of the file suffixed by ".pub" to the field labeled "Key" before clicking "Add SSH key" below those fields.

## Cloning and configuring the repositories
1. Clone each of the project repositories:
    * https://github.com/pkmn-tools/front_end.git
    * https://github.com/pkmn-tools/back_end.git
    * https://github.com/pkmn-tools/documents.git

     Decide on the directory you wish to store the projects in (for example, I chose /Users/landon/pokemon/tcg/pkmn.tools/). If the directory does not already exist, you will need to create the directory and then navigate into it before cloning the repositories.

     ```
 mkdir -p /path/to/desired/directory
 cd /path/to/desired/directory
 GIT_SSH_COMMAND="ssh -i /path/to/your/ssh/privatekey" git clone git@github.com:pkmn-tools/documents.git
 GIT_SSH_COMMAND="ssh -i /path/to/your/ssh/privatekey" git clone git@github.com:pkmn-tools/front_end.git
 GIT_SSH_COMMAND="ssh -i /path/to/your/ssh/privatekey" git clone git@github.com:pkmn-tools/back_end.git
 GIT_SSH_COMMAND="ssh -i /path/to/your/ssh/privatekey" git clone git@github.com:pkmn-tools/server.git
 ```

     Note: This may prompt you to enter your password multiple times. This is normal, and do not be surprised if it does not show you anything as you type the password.

2. Configure git to use your private SSH key all the time

 Then you will need to configure the repository and all submodules to use your ssh key as well

 ```
 cd /path/to/desired/directory/documents
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 cd /path/to/desired/directory/front_end
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 cd /path/to/desired/directory/back_end
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 cd /path/to/desired/directory/server
 git config core.sshCommand "ssh -i /path/to/your/ssh/privatekey"
 ```

