# code-server (VS Code) on the ETH Zürich Euler cluster
<img width="20%" src="https://upload.wikimedia.org/wikipedia/commons/9/99/ETH_Z%C3%BCrich_Logo_black.svg" />
<img width="5%" src="https://upload.wikimedia.org/wikipedia/commons/9/9a/Visual_Studio_Code_1.35_icon.svg" />

**code-server** allows you to run Visual Studio Code on any machine anywhere and access it in the browser. (https://github.com/coder/code-server)

This repository contains a script to start **code-server** from a local computer on Euler and connect it with a local browser.

*The script was adapted from Samuel Fux, Andreas Lugmayr, Mike Boss, and Nadia Marounina (https://gitlab.ethz.ch/sfux/VSCode_remote_HPC)*

```{bash}
Usage: start_vscode [options]

Options:
        -u | --username       USERNAME         ETH username for SSH connection to Euler
        -n | --numcores       NUM_CPU          Number of CPU cores to be used on the cluster
        -W | --runtime        RUN_TIME         Run time limit for the code-server in hours, minutes, and seconds HH:MM:SS
        -m | --memory         MEM_PER_CPU      Memory per CPU limit in MB
Optional arguments:
        -c | --config         CONFIG_FILE      Configuration file for specifying options
        -g | --numgpu         NUM_GPU          Number of GPUs to be used on the cluster
        -h | --help                            Display help for this script and quit
        -i | --interval       INTERVAL         Time interval for checking if the job on the cluster already started
        -k | --key            SSH_KEY_PATH     Path to SSH key with non-standard name
        -v | --version                         Display version of the script and exit
        
Examples:
        start_vscode -u josousa -n 1 -W 04:00:00 -m 2048
        start_vscode --username josousa --numcores 1 --runtime 01:00:00 --memory 2048
        start_vscode -c $HOME/.vsc_config
        
Format of configuration file:
VSC_USERNAME=""             # ETH username for SSH connection to Euler
VSC_NUM_CPU=1               # Number of CPU cores to be used on the cluster
VSC_NUM_GPU=0               # Number of GPUs to be used on the cluster
VSC_RUN_TIME="01:00:00"     # Run time limit for the code-server in hours, minutes, and seconds HH:MM:SS
MEM_PER_CPU=2048            # Memory per CPU limit in MB
VSC_WAITING_INTERVAL=10     # Time interval to check if the job on the cluster already started
VSC_SSH_KEY_PATH=""         # Path to SSH key with non-standard name
```
