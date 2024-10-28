[C3L: Cluster Centroids Contrastive Learning for High-Level Semantic-Aware Reinforcement Learning]

Our code is based on [CURL](https://github.com/MishaLaskin/curl).

## Installation for DMControl

```
Libraries (Required libraries can be different based on the settings.)
- conda, python (3.11.5)
- gym (0.17.3)
- git
- pytorch, https://pytorch.org/
- dmc2gym, pip install git+https://github.com/denisyarats/dmc2gym.git (change np.int(~) -> int(~) in the wrapper.py file in cf. C:\Users\owner\anaconda3\envs\gymenv\Lib\site-packages\dmc2gym)
- scikit-learn
- matplotlib
- scikit-image
- termcolor
- tensorboard
```

## Instructions
To train a C3L agent on the `cheetah, run` task using image-based observations, configure the environments and hyperparameters in the `train.py` file, then execute the `train.py` file.

In your console, you should observe printouts similar to the following:
```
| train | E: 0 | S: 6000 | D: 513.1 s | R: 0.0000 | BR: 0.0000 | A_LOSS: 0.0000 | CR_LOSS: 0.0000 | C3L_LOSS: 0.0000
| train | E: 25 | S: 6500 | D: 389.9 s | R: 83.2496 | BR: 0.1873 | A_LOSS: -9.1030 | CR_LOSS: 0.1168 | C3L_LOSS: 1.9664
| train | E: 27 | S: 7000 | D: 0.0 s | R: 29.1004 | BR: 0.2005 | A_LOSS: -9.8642 | CR_LOSS: 0.1332 | C3L_LOSS: 2.1396
| eval | S: 7000 | ER: 124.3240
```

Log abbreviation mapping:
```
train - training episode
E - total number of episodes 
S - total number of environment steps
D - duration in seconds to train 1 episode
R - mean episode reward
BR - average reward of sampled batch
A_LOSS - average loss of actor
CR_LOSS - average loss of critic
C3L_LOSS - average loss of the C3L encoder
```


## Installation for Atari

```
Libraries (Required libraries can be different based on the settings.)
- conda, python (3.10.13)
- pytorch, https://pytorch.org/
- atari_py
- ROM download, http://www.atarimania.com/rom_collection_archive_atari_2600_roms.html
- 7.zip to unpack long name directories, https://www.7-zip.org/
- Unpack rom in cf. C:\Users\owner\anaconda3\envs\atari_env\Lib\site-packages\atari_py\atari_roms\Atari-2600-VCS-ROM-Collection ( ex. python -m atari_py.import_roms C:\Users\owner\anaconda3\envs\atari_env\Lib\site-packages\atari_py\atari_roms\Atari-2600-VCS-ROM-Collection )
- kornia
- opencv-python
- plotly
- tqdm
- hydra-core
- pandas
```

## Instructions
To train a C3L agent on the `kung_fu_master` task using image-based observations, configure the environments and hyperparameters in the `main.py` file, then execute the `main.py` file.

In your console, you should observe printouts similar to the following:
```
                          id: cccl-cc+ic-kung_fu_master-0
                          seed: 0
                          disable_cuda: False
                          game: kung_fu_master
                          version: cc+ic
                          T_max: 100000
                          max_episode_length: 108000     
                          history_length: 4
                          architecture: data-efficient   
                          hidden_size: 256
                          noisy_std: 0.1
                          atoms: 51
                          V_min: -10
                          V_max: 10
                          model: None
                          memory_capacity: 100000
                          replay_frequency: 1
                          priority_exponent: 0.5
                          priority_weight: 0.4
                          multi_step: 20
                          discount: 0.99
                          target_update: 2000
                          reward_clip: 1
                          learning_rate: 0.0001
                          adam_eps: 0.00015
                          norm_clip: 10
                          learn_start: 1600
                          evaluate: False
                          evaluation_interval: 20000
                          evaluation_episodes: 100
                          evaluation_size: 500
                          render: False
                          enable_cudnn: False
                          checkpoint_interval: 0
                          memory: None
                          disable_bzip_memory: False
                          batch_size: 32
                          tolerance_eps: 0.2
                          tolerance_samples: 0.1
                          cccl_update_freq: 50
                          cccl_coeff: 0.5
  2%|███                                                                                                                                                                                    | 1660/100000 [00:19<3:07:52,  8.72it/s]
```
