# Safe Multi-Agent Reinforcement Learning with Policy Optimisation 

The repository is for the paper: **Safe Multi-Agent Reinforcement Learning with Policy Optimisation**, in which we investigate the problem of safe MARL. The problem of safe multi-agent learning with safety constraints has not been rigorously studied; very few solutions have been proposed, nor a sharable testing environment or benchmarks.   To fill these gaps, in this work, we formulate the safe multi-agent reinforcement learning problem as a constrained Markov game and solve it with trust region methods. Our solutions---*Multi-Agent Constrained Policy Optimisation (MACPO)* and *MAPPO-Lagrangian*---leverage on the theory of  *Constrained Policy Optimisation (CPO)* and multi-agent trust region learning, and critically, they enjoy theoretical guarantees of  both  monotonic improvement in reward and satisfaction of safety constraints  at every iteration. Experimental results reveal that  *MACPO/MAPPO-Lagrangian* significantly outperform baselines in terms of balancing the performance and constraint satisfaction, e.g. [MAPPO](https://arxiv.org/abs/2103.01955), [IPPO](https://arxiv.org/abs/2011.09533), [HAPPO](https://arxiv.org/abs/2109.11251).



## Environments Supported:

- [Safe Multi-Agent Mujoco](https://github.com/Anonymous-ICML2022/Safe-Multi-Agent-Benchmarks/tree/main/Safe-Multi-Agent-Mujoco)
- [Safe Multi-Agent Robosuite](https://github.com/Anonymous-ICML2022/Safe-Multi-Agent-Benchmarks/tree/main/Safe-Multi-Agent-Robosuite)




## 1. Installation

####  1.1 Create Environment

``` Bash
# create conda environment
conda create -n macpo python==3.7
conda activate macpo
pip install -r requirements.txt
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia
```

```
cd MACPO/macpo (for the macpo algorithm) or cd MAPPO-Lagrangian/mappo_lagrangian (for the mappo_lagrangian algorithm)
pip install -e .
```



#### 1.2 Install Safety Multi-Agent Mujoco


- Install mujoco accoring to [mujoco-py](https://github.com/openai/mujoco-py) and [MuJoCo website](https://www.roboti.us/license.html).
- clone [Safe Multi-Agent Mujoco](https://github.com/Anonymous-ICML2022/Safe-Multi-Agent-Benchmarks/tree/main/Safe-Multi-Agent-Mujoco) or [Safe Multi-Agent Robosuite](https://github.com/Anonymous-ICML2022/Safe-Multi-Agent-Benchmarks/tree/main/Safe-Multi-Agent-Robosuite) to the env path (in this repository, have set the path).

``` Bash
LD_LIBRARY_PATH=${HOME}/.mujoco/mujoco200/bin;
LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so
```



## 2. Train

```
cd MACPO/macpo/scripts or cd MAPPO-Lagrangian/mappo_lagrangian/scripts
chmod +x ./train_mujoco.sh
./train_mujoco.sh
```







<!-- ## Acknowledgments

Some sections of the repository are based on [MAPPO](https://github.com/marlbenchmark/on-policy), [HAPPO](https://github.com/cyanrain7/Trust-Region-Policy-Optimisation-in-Multi-Agent-Reinforcement-Learning), [safety-starter-agents](https://github.com/openai/safety-starter-agents), [CMBPO](https://github.com/anyboby/Constrained-Model-Based-Policy-Optimization). -->





