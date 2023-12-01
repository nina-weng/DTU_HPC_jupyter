
### Short Intro
This note is for people who want to use jupyter notebook with DTU HPC, especially for using GPU resources on notebooks. The method we provide here is using VSCode tunnels. This note is mainly written down by me, with plenty help from Eike Petersen, who set up the procedure initially. 

### Important information
* If you are new to DTU HPC, please check their guidance before everything: https://www.hpc.dtu.dk/
* Please remember that it is NOT allowed to run heavy task on login node.
* Please remember that interactive nodes should NOT be used for heavy task, instead, it should be mainly used for development, profiling and testing. (check: https://www.hpc.dtu.dk/?page_id=2129) Once the code is ready, you should run it as the form of job-submitting on clusters( check here for how to submit job using GPU: https://www.hpc.dtu.dk/?page_id=2759). 


# A simple guideline of using VSCode tunnels for firing jupyter notebook on HPC

You need to prepare your remote and local environment as follows: 

## Set up remote environment
1. log on to interactive node using linuxsh(non-GPU needed) or a100sh/voltash (GPU needed) **(DO NOT FORGET THIS STEP, we are not allowed to run heavy task on the log-in node)**
2. Set up a virtual python environment at HPC, install jupyter and other packages you need 
	* You can do this in two ways: building a virtual environment directly or using conda to build it. More details please refer to: https://www.hpc.dtu.dk/?page_id=3678 
3. Install the CLI on the remote machine 
````
curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=cli-alpine-x64' --output vscode_cli.tar.gz

tar -xf vscode_cli.tar.gz
````
4. run "./code tunnel"; the first time it will ask you to sign in to github and paste some activation code; after that it will just start up the tunnel and give you a link. Using the link, you can also access the remote machine by browsers; here we also provide another method using VSCode editor. 

## Set up local environment
1. install VSCode
2. Connect to the tunnel using VSCode Remote-SSH ("Connect to tunnel")
3. And now you can open the notebook at VSCode and run with HPC clusters :)

## Some other tips
1. Sometimes the notebook can not get the right python environment from tunnel, you will need to set it up by yourself by changing the **kernels** on the right top in VSCode window. 
	* *If the kernel is not on the drop-down options*, you can use shortcuts: Ctrl+Shift+P, then choose "Python: Select Interpreter", then "Enter interpreter path"
2. It might stuck if the last tunnel session didn't exit nicely, in this case, you can kill the corresponding `qrsh` job in the cluster (the job for running tasks on the interactive node).
	* *How to proper exit the tunnels*: press 'ctrl+c' and exit the interactive node.

More instructions here: https://code.visualstudio.com/docs/remote/tunnels

Have fun!
:)


