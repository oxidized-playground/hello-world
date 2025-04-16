# Preparations for the Rust playground

This guide will prepare you for the Rust playground. Once finished you will have everything you need (and pre-downloaded) to build and run Rust.

## Prerequisites
- VSCode
- Github access

## Getting the stuff on your PC

Clone this git repository into a folder on your PC with either HTTPS or SSH.

`git clone https://github.com/oxidized-playground/hello-world.git`

![Clone the repo](/images/clone_repo.png "Clone the repo")

- Open the repository in VSCode
  
**Note:** VSCode will ask you to install suggested extensions. Ignore this for now. 

VSCode will now ask you to reopen the directory in a devcontainer

![Reopen in container](/images/reopen_in_container.png "Reopen in container")

- Click reopen
- Install WSL if the system prompts you to

![install WSL](/images/install_wsl.png "Install WSL")

- Reboot your PC when finished

**Note:** This step might fail the first time, so you might need to run it a second time if the first time fails. 

**Note:** When WSL is installed a WSL windows may appear, ignore this.

After successfully installing WSL, VSCode will ask you to continue opening the folder into the devcontainer. 

![Successful install](/images/continue_opening_in_devcontainer.png "Successful install")

- Press continue

**Note:** You might encounter an issue here (see image). To solve this, look at the bottom of the page for instructions.
![No permission](/images/no_permission_to_run_docker.png "No permission")

A new VSCode window will open and (when looking at the log) the devcontainer will create itself. this takes a little bit of time, please have patience. 

![Installing container](/images/installing_devcontainer.png "Installing container")

When this is done, VSCode will again ask to install suggested extensions this time inside the devcontainer.

![Install extensions](/images/install_extensions.png "Install extensions")

- Press install

## Try to build hello world

- Navigate to src/main.rs in the project folder

- Press Run right above the fn main() line
this should yield the following outcome

![Run](/images/run.png "Run")

And the resulting output:

![Output](/images/run_result.png "Output")

**Note:** You can also use a new terminal and type cargo run, this is the same as running it from the codeblock

![Run manually](/images/run_manually.png "Run manually")


## Troubleshooting Docker

When you get this message when trying to open the folder in a devcontainer, the install process was not able to correctly setup your docker environment. 
This is because something went wrong assigning the user to the docker group, which requires root level permissions and the installer was not able to get these permissions through sudo. If you try to run something with sudo yourself it will ask for a password that you don't have so we need to change it first for the "devcontainers" user. 
Execute the following steps in a terminal to solve this manually.


- wsl -u root
- passwd devcontainers
- Now type in any password you like, it can be anything
  but make sure to remember it
- exit

---

- wsl
- sudo usermod -aG docker $USER
- sudo reboot now

**Note:** it will take a bit of time to restart the devcontainer, so wait a couple minutes before trying to continue opening the devcontainer in VSCode









  

