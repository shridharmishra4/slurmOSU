### Unofficial Guide to hpc-cluster at OSU.

This is an unofficial guid on how to request for resource and fairly use them for research. 

### Available Nodes
`sinfo -o "%N %c %G %l %f" `

| PARTITION | NODELIST                                                       | CPUS | GRES          | TIMELIMIT   | AVAIL_FEATURES        |
|-----------|----------------------------------------------------------------|------|---------------|-------------|-----------------------|
| share     | cn-d-5                                                         | 40   | (null)        | 7-00:00:00  | broadwell             |
| share     | cn-h-8,cn-i-5                                                  | 24+  | (null)        | 7-00:00:00  | skylake               |
| share     | cn-0-[1-9],cn-1-[1-9],cn-2-[1-9],cn-3-12,cn-4-[3-4],cn-5-[1-9] | 12   | (null)        | 7-00:00:00  | x5650                 |
| share     | cn-7-[1-2,4-9,11-15],cn-8-[1-8,11-13,15]                       | 8    | (null)        | 7-00:00:00  | harpertown            |
| share     | cn-9-[2-4]                                                     | 12   | (null)        | 7-00:00:00  | sandybridge           |
| share     | cn-e-[7-8]                                                     | 20   | (null)        | 7-00:00:00  | haswell               |
| share     | cn-g-[01-08]                                                   | 8    | (null)        | 7-00:00:00  | opteron               |
| share     | cn-h-4                                                         | 40   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,gtx1080       |
| share     | cn-j-4                                                         | 32   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,g6130,gtx980  |
| sharegpu  | cn-f-5                                                         | 20   | gpu:2         | 7-00:00:00  | haswell,e5-2660v3,m60 |
| sharegpu  | cn-h-4                                                         | 40   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,gtx1080       |
| sharegpu  | cn-j-4                                                         | 32   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,g6130,gtx980  |
| sharegpu  | compute-gpu                                                    | 24   | gpu:2         | 7-00:00:00  | haswell,m60           |
| dgx2      | compute-dgx2-[1-6]                                             | 96   | gpu:16(S:0-1) | 7-00:00:00  | skylake,v100          |
| gpu       | cn-gpu[1-2]                                                    | 20   | gpu:8         | 7-00:00:00  | haswell,gtx1080       |
| gpu       | cn-gpu5                                                        | 40   | gpu:8(S:0-1)  | 7-00:00:00  | skylake,g6248,rtx8000 |
| gpu       | compute-gpu[3-4]                                               | 20   | gpu:8(S:0-1)  | 7-00:00:00  | haswell,rtx2080       |
| dgx       | compute-dgx2-[4-6]                                             | 96   | gpu:16(S:0-1) | 7-00:00:00  | skylake,v100          |
| dgxs      | compute-dgxs-[1-3]                                             | 40   | gpu:4         | 2-00:00:00  | broadwell,v100        |
| class     | compute-dgxs-[1-3]                                             | 40   | gpu:4         | 1:00:00     | broadwell,v100        |
| eecs      | cn-0-[1-9],cn-1-[1-13],cn-2-[1-12]                             | 12+  | (null)        | 7-00:00:00  | x5650                 |
| eecs3     | cn-f-[1-4]                                                     | 20   | (null)        | 7-00:00:00  | haswell,e5-2660v3     |
| eecs3     | cn-f-5                                                         | 20   | gpu:2         | 7-00:00:00  | haswell,e5-2660v3,m60 |
| mime1     | cn-a-[1-2]                                                     | 16   | (null)        | 7-00:00:00  | sandybridge           |
| mime2     | cn-c-[01-06]                                                   | 16   | (null)        | 7-00:00:00  | ivybridge,e5-2650v2   |
| mime2     | cn-c-[11-12]                                                   | 16   | (null)        | 7-00:00:00  | haswell,e5-2630v3     |
| mime3     | cn-d-[1-5]                                                     | 28+  | (null)        | 15-00:00:00 | broadwell             |
| mime4     | cn-l-[1-2]                                                     | 20   | (null)        | 7-00:00:00  | skylake               |
| mime4     | cn-e-1                                                         | 20   | gpu:1         | 7-00:00:00  | haswell,k40m          |
| mime4     | cn-e-[2-8]                                                     | 20   | (null)        | 7-00:00:00  | haswell               |
| mime5     | cn-h-[1-3]                                                     | 40   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,gtx1080       |
| mime5     | cn-h-[5-7]                                                     | 44   | (null)        | 7-00:00:00  | skylake               |
| mime6     | cn-j-4                                                         | 32   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,g6130,gtx980  |
| mime7     | cn-k-[1-2]                                                     | 20   | (null)        | 7-00:00:00  | skylake               |
| cbee      | cn-b-[1-6]                                                     | 16   | (null)        | 7-00:00:00  | ivybridge,e5-2650v2   |
| cbee      | cn-i-[1-5]                                                     | 24   | (null)        | 7-00:00:00  | skylake               |
| forestry  | cn-9-[1-4]                                                     | 12   | (null)        | 7-00:00:00  | sandybridge           |
| cascades  | cn-m-1                                                         | 8    | gpu:6(S:0-1)  | 7-00:00:00  | skylake,t4            |
| cascades  | cn-m-2                                                         | 16   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,rtx6000       |
| nacse     | cn-3-[1-11]                                                    | 12   | (null)        | 7-00:00:00  | x5650                 |
| nacse     | cn-n-[1-6]                                                     | 36   | (null)        | 7-00:00:00  | skylake               |
| nerhp     | cn-4-[3-4]                                                     | 12   | (null)        | 7-00:00:00  | x5650                 |
| nerhp     | cn-4-[5-8]                                                     | 28   | (null)        | 7-00:00:00  | skylake,gold          |
| chem      | cn-g-[01-08]                                                   | 8    | (null)        | 7-00:00:00  | opteron               |
| matsci    | cn-5-[2-9]                                                     | 12   | (null)        | 7-00:00:00  | x5650                 |
| preempt   | cn-gpu[1-2]                                                    | 20   | gpu:8         | 7-00:00:00  | haswell,gtx1080       |
| preempt   | cn-m-1                                                         | 8    | gpu:6(S:0-1)  | 7-00:00:00  | skylake,t4            |
| preempt   | compute-gpu[3-4]                                               | 20   | gpu:8(S:0-1)  | 7-00:00:00  | haswell,rtx2080       |
| preempt   | cn-1-[10-13],cn-2-[10-12],cn-5-[10-12]                         | 12+  | (null)        | 7-00:00:00  | x5650                 |
| preempt   | cn-4-[5-8]                                                     | 28   | (null)        | 7-00:00:00  | skylake,gold          |
| preempt   | cn-9-1                                                         | 12   | (null)        | 7-00:00:00  | sandybridge           |
| preempt   | cn-b-[1-5]                                                     | 16   | (null)        | 7-00:00:00  | ivybridge,e5-2650v2   |
| preempt   | cn-c-[11-12]                                                   | 16   | (null)        | 7-00:00:00  | haswell,e5-2630v3     |
| preempt   | cn-h-[1-3]                                                     | 40   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,gtx1080       |
| preempt   | cn-h-[5-7],cn-i-[1-4]                                          | 24+  | (null)        | 7-00:00:00  | skylake               |
| preempt   | cn-m-2                                                         | 16   | gpu:2(S:0-1)  | 7-00:00:00  | skylake,rtx6000       |


###  [Getting Started](https://it.engineering.oregonstate.edu/hpc/getting-started)
 
#### Obtain an COE account
To use the CoE HPC, you must have an engineering account and be sponsored by a primary investigator.


#### SSH access
You must use an SSH client app to connect to the CoE HPC cluster.  If you are using Linux or a Mac computer, then you 
can just use the ssh command to connect to any one of the three CoE HPC submit hosts (submit-a, submit-b, submit-c), 
e.g.:

ssh myEngrAcct@submit-a.hpc.engr.oregonstate.edu
If you are using Windows, you need to download an SSH client like MobaXterm or Putty.


#### Reserving cluster resources over [screen](https://linuxize.com/post/how-to-use-linux-screen/):
We may either use screen or tmux to keep the session alive for running long jobs like ML model training. Once the 
resource is allocated one can directly ssh to the allocated server and run the tasks upto the TIMELIMIT in the above 
table.

Here's a quick guide on how to do that:
Login to CoE HPC submit hosts (submit-a, submit-b, submit-c) 


- On the command prompt, type screen.
- Run the desired program `srun -A eecs -p dgx2 --time 7-0 -c 4 --gres=gpu:1 --mail-user=mishrash@oregonstate.edu --mail-type=ALL bash`
 for 7 days, 4 cpus and 1 gpu.
- Use the key sequence Ctrl-a + Ctrl-d to detach from the screen session.
- Exit submit server using ctrl + c.

At this point you might get a resource allocation immediately or you may have to wait until the requested resource is 
available. Once the resource has been allocated you should receive an email if configured. You may check the node by:
 - Login to any submit server.
 - Type  `squeue -u mishrash`
 - It would look something like 
 `68985      dgx2     bash mishrash  R    2:46:24      1 compute-dgx2-6`

To [reattach](https://linuxize.com/post/how-to-use-linux-screen/#detach-from-linux-screen-session) screen(optional):

 - Login to same submit server.
 - Type `submit -ls` and copy the session id 
- Reattach to the screen session by typing screen -r <session-id>.

#### Log into allocated resource

Once the resource has been allocated you may log into the alocated node directly as if you had direct access to the node
until TIMELIMIT. You may open as many terminal as required for multiple tasks

For example:
`ssh mishrash@compute-dgx2-6.hpc.engr.oregonstate.edu`


### Tips and Tricks:

- Type `module avail` for knowing about different versions of compiles like gcc, cuda etc. Load the required package with
`module load cuda/10.1 or module load gcc/7.5`
- VNC on remote server:
    - After logging into remote server type `vncserver -geometry 1024x720`
    - From local server open a new terminal and setup port forwarding to `ssh -L5901:localhost:5901 mishrash@compute-dgx2-6.hpc.engr.oregonstate.edu`
    - Donwload and install vnc viewer and a new connection with vnc server as `localhost:5901`.
- Check cluster load with `sinfo -o "%n %c %e %G %O" -p dgx2`
- Allocate a sepeific node with `srun -A eecs -p dgx2 -w compute-dgx2-2 --time 7-0 -c 8 --gres=gpu:1 bash`


#### With great power comes great responsibilities!
Currently the Slurm limits are as follows:

- 32 total jobs, 16 running jobs
- 16 gpus per user at a time (e.g. either 1 job with 16 gpus or 2 jobs with 8, or 4 jobs with 4, etc.)
- 32 cpus per user at a time
- 12 hours default walltime limit, 7 days maximum walltime limit

which gives immense compute capabilities to the faculty and students which if you think about is upto 512 gb of graphic 
memory which is accessible on dgxs however these resources are shared with hundreds of students and faculty members so its highly recommended to only 
request for resources which is required and not solely just because you can. 

Some ways to ensure fair usage could be:
- Checking for utilization of current resources before requesting for additional gpu resources.
- For example if someone is trying to tune the hyperparameters consider training different experiments on same gpus with 
smaller batch size to max out the gres memory before allocating an additional gpu, someone else might need gpus too.





#### Useful Links:
- [Getting Started](https://it.engineering.oregonstate.edu/hpc/getting-started)
- [sinfo](https://slurm.schedmd.com/sinfo.html)
- [FAQS](https://it.engineering.oregonstate.edu/hpc/faqs)
- [Mailing List](https://it.engineering.oregonstate.edu/mailman/listinfo/cluster-users)

###### Author: Shridhar Mishra (mishrash at oregonstate.edu)
###### Date: 28 Aug 2020