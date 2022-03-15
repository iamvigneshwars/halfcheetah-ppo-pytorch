# AI-Walkers-ppo-pytorch

Pytorch implimentation of proximal policy optimization with clipped objective function and generalized advantage estimation. The model is trained on Humanoid, hopper, ant and halfcheetah pybullet environment. To run multiple environments in multiple threads, SubprocVecEnv class from stable baseline is used (file included).

## Usage
Important command line arguments : <br>
`--env` environment name (note : works only for continuous pybullet environments) <br>
`--learn` agent starts training <br>
`--play` agent plays using pretrained model <br>
`-n_workers` number of environments <br>
`-load` continues training from given checkpoint <br>
`-model` load the model or checkpoint <br>
`-ppo_steps` number of steps before update <br>
`-epochs` number of updates <br>
`-mini_batch` batch size during ppo update <br>
`-lr` policy and critic learning rate <br>
`-c1` critic discount <br>
`-c2` entropy beta <br>

To train the agent:
```
# train new agent
python agent.py --learn --env <ENV_ID> 

# load checkpoints
python agent.py --learn --env <ENV_ID> -load -model <CHECKPOINT PATH> 

```
To Play: 
```
python agent.py --play --env <ENV_ID> -model <MODEL PATH>

```
