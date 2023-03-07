# Running Stability Experiments

The experiments in this folder were all done to try to overcome the hanging and crashing of the training after ~3-4h of running.

The actual nuances of setup of the experiment m4-wise didn't matter at all, I just forked one of the recent experiments.

The main discovery so far is using Deepspeed-v0.6.7 + a fix seems to be doing great, see [this logbook](tr_141_cm409xPMD01_scale_leap_of_faith_v5_num_workers_04/).
