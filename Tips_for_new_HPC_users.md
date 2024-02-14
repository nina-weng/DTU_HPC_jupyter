
Hej again:) As always, I was very struggling when first trying HPC many years ago. Therefore, I hope that as an old user, I can provide some useful tips for new users of HPC. 

#### A. Where are the useful links on the HPC official webpage
Not surprisingly, there is a [document](https://www.hpc.dtu.dk/?page_id=3226) for the use of HPC. And not surprisingly, it is not that well organised so sometimes I find it hard to find what I need by clinking. Here I summarised some useful links on HPC official webpage in the form of a Q&A:

**Extra note before the Q&A:**
I would like first to refer anybody to try to click here and there on the official HPC webpage to get as much information as possible. You will not need to remember anything but play around with it and know which tab might lead to useful links. 

##### 0. Linux? Never heard of
Ah ha. Congrats, you have a chance to learn so much. My best suggestion in the era is to ask GPT about your request. e.g. "how can I check the size of the folder". 
Again, GPT is magical. (Also, remember that they might give you the wrong answer.) 

##### 1. How to build a virtual environment on HPC (conda)
[page](https://www.hpc.dtu.dk/?page_id=3678) under *"Virtual environments"* and *"Miniconda"*

##### 2. How to submit jobs on HPC
[page](https://www.hpc.dtu.dk/?page_id=1416), sample scripts could also be found there.

##### 3. How to submit jobs using GPU on HPC
[page](https://www.hpc.dtu.dk/?page_id=2759)

##### 4. Can I use the GPU resources interactively for testing
Yes, check [page](https://www.hpc.dtu.dk/?page_id=2129) under "Running interactively on GPUs".
Note that the interactive nodes should mainly be used for development, profiling, and short test jobs. Avoid heavy jobs for interactive nodes.

Check the availability of the interactive nodes: 
`nvidia-smi`

##### 5. Run out of space
[page](https://www.hpc.dtu.dk/?page_id=927)

##### 6. Why did my submitted job never get started
This could be caused by multiple reasons:
* queue is very busy at the moment; check `bqueues -l name_of_nodes
* request too many resources that it could give (GPU nodes for example)
* the cluster is going to be shut down soon (e.g. 10 hours), and you submit a job that requires more than 10 hours
* ...



#### B. How to better edit my code on HPC
##### B.1 Via VScode
Note: the choice of how to edit code is very personal. It's more important to find the way you are fond of than try different ways. 

If you'd like to use vs code for editing code/project management on HPC:
* Open the vs code software
* click "open the remote window" (button on the left-down corner) and input your username and password; vscode should be able to auto-remember your login information.
* Open the directory you need to work on
* edit the code as you want, but do NOT run notebooks on login nodes (check [this file](README.md)).



Have fun:)