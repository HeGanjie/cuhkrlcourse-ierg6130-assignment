# IERG 6130: Reinforcement Learning and Beyond

Welcome! This is the codebase for assignments of our reinforcement learning (RL) course. 

As this course is still polishing and growing, please feel free to open issues if you find anything wrong or confusing in codes or documents in this repository. We will respond to you as soon as possible. If you get stuck or mess up, take a look at the latest version of this repo may help, since somebody may already raise issues and bug is fixed by new commits.

The email address for you to submit assignments is: cuhkrlcourse@googlegroups.com . Follow the instruction in each assignment's `README.md` to submit your work.

**We appreciate you for suggestion and contribution to improve this course!**



## General procedure of using this repo

Generally, the way you use this repo is:

1. Check the latest release at the time the tutor announced a new assignment is coming.
2. Read the assignment document, which is the `README.md` at each assignment directory.
3. Copied or fork or somewhat get the codes (or jupyter notebook) at your computer.
4. Fill the empty functions or slots or cells we left for you.
5. Follow the instructions in code comments to check if everything works well.
6. Submit materials to correspondent staff, following the submission instruction in the assignments.

Beautiful codes and comments make extra credits. Our aesthetic standard is [PEP 8](https://www.python.org/dev/peps/pep-0008/).



## Environment setup instruction

In this course, we require you to have the basic knowledge of python. In each assignment, which is codes work written by python, we may use some packages to help you. For example the reinforcement learning environment [Gym](https://gym.openai.com/), scientific computing [Numpy](https://numpy.org/), machine learning framework [PyTorch](https://pytorch.org/) etc.

We will list the packages required at each assignment. So till now, you only need to set up your python environment first. We highly recommend you to use python 3, since python 2 is gradually getting deprecated in community. If you already have one, then you can skip the next section.

The general procedure of environment setup is:

1. Prepare your python environment
2. Install Jupyter notebook and Gym as they are used at each assignment
3. Install packages we listed in each assignment
4. If you use other packages, list their names and versions at your report



## Setup your virtual environment

We recommend you to use a virtual environment to setup the python environment. This is optional, but has many advantages for doing this:

1. The packages installed during this course will not affect other projects on your computers since the environment is independent of other projects.
2. Other members can run your codes in this course seamless. Since we all using the same environment and packages.
3. The robustness and compatibility of codes is also an important criterion to assess your completion of assignments. This is because if the program is not runnable at TA's computer, your code is considered as not runnable. So, you know.
4. In your future research career, a clear and ordered code management is the key to success.

We recommend you to use anaconda python environments. First, download the package and install anaconda following the instruction at https://www.anaconda.com/distribution/

Then create your environment via typing command line:

```
conda create -n ierg6130 python=3.7
```

By doing this, you created an environment name `IERG6130` with python 3.7.5 installed. Then you need to activate your environment before running your codes such as `jupyter notebook` or `python FILE.py` or installing a package like `pip install XXX`:

```
conda activate ierg6130
```

If you activate your successfully, you will see `(ierg6130) COMPUTERNAME:~ USERNAME$` at your shell.

Then you can install the packages we listed at each assignment like:

```
pip install XXX=1.0.0
```

where the `XXX=1.0.0` means to install package `XXX` with the specified version `1.0.0`. The packages' names and versions will be listed at each assignment.

If you use other packages that you think helpful, you need to list them with the version number at your report. Make sure the extra package DO NOT help you to finish the essential part of the assignment. The following example is NOT acceptable.

```python
import numpy as np
from SmartGuyWroteKLDivergencePackage import get_kl

def compute_kl(dist1, dist2):
    """
    Problem 1: You need to implement the computing of KL
    Divergence given two distribution instances.
    
    You should only use numpy package.
    
    The return should be a float that greater than 0.
    """
    return get_kl(dist1, dist2)
```



## Install and use  jupyter notebook

In some assignments, we may provide you with a single jupyter notebook file. Note that we use the "classic jupyter notebook" instead of the latest jupyter lab. Before you open it, you need to install the package (if you use a virtual environment, remember to activate it before installation)

```
pip install notebook
```

Now you have installed the jupyter notebook. Go to the directory  `FILE.ipynb` located, command:

```
jupyter notebook
```

Now you have opened up a jupyter notebook at your server. Open your browser and go to `http://localhost:8888`  (8888 is the port number, you can change it by starting jupyter notebook via `jupyter notebook --port 8889`).

Now click into `FILE.ipynb` and start coding!

For more information, please visit: https://jupyter.org/install.html



## Install and use Gym

Gym provides you many handy RL environments (this "environment" is different from the "python environment" previously seen), so you can easily use the interfaces to conduct your RL research. For example, you do not need to implement a Go game to train your alphaGo, you only need to call the API provided by Gym. By the way, in this course, we do not require you to implement alphaGo.

To install Gym, in command line type:

```
# activate your environment
conda activate ierg6130

# install it
pip install gym
```

This is it. Now you can run it in ipython for a little test.

```
# type in command line (ipython should already be installed by anaconda)
ipython
```

Now you have enter ipython, copy and paste:

```python
import gym
env = gym.make('CartPole-v0')
env.reset()
for _ in range(500):
    env.render()
    # take a random action
    obs, reward, done, info = env.step(env.action_space.sample())
    if done:
        env.reset()  # press q to quit
env.close()
```

You will see a window pop up at your computer. Type `quit()` and enter in ipython to leave. 

Congratulation, you have installed gym. Now click the directory and start your assignments! 



------

*2019-2020 2nd term, IERG 6130: Reinforcement Learning and Beyond. Department of Information Engineering, The Chinese University of Hong Kong. Course Instructor: Professor ZHOU Bolei. Assignment author: PENG Zhenghao.*