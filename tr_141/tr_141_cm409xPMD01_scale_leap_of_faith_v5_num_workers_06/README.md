# experiment 6.1

## TLDR

like 4.1, using old deeepspeed 0.6.7+patch, but also trying low grad clip of 0.3

Run into a node failure and slurm killing the training this time.

Crash-wise is inconclusive - thinking that this was an unrelated HW problem.

But we made a huge progress 2500 iterations and 8h of run! Definitely this is much much better!


### Setup

```
cd /gpfsdswork/projects/rech/cnw/commun/experiments/stas/m4-full
bash experiments/pretraining/vloom/tr_141_cm409xPMD01_scale_leap_of_faith_v5_num_workers_06/01_launch.sh

cd /gpfsssd/scratch/rech/cnw/commun/experiments/local_experiment_dir/tr_141_cm409xPMD01_scale_leap_of_faith_v5_num_workers_06/logs
tail -f main_log.txt
```


- m4@main - no tweaks
- conda env stas-m4
- pip install deepspeed==0.6.7
- pt-1.12
- grad_clip: 0.3
- CUDA_LAUNCH_BLOCKING=1
- num_workers=2
- normal accumulation (really using m4@main)



### Investigation

```
iteration:  2500/500000   0% | elapsed time: 07:41:19 | per_token_loss: 3.1525 | lr: 9.990E-06 | num_tokens: 788088885 | num_images: 26284370 | num_padding: 391115 | fwd_bwd_time: 43621.8 | fwd_bwd_time_no_acc: 17.3 | image_to_text_ratio: 0.0332 | num_batches: 2500 | num_batches_in_curr_epoch: 706 | num_batches_since_training_logged: 25 | num_epochs: 1 | num_opt_steps: 2500 | z_loss: 24.6600 | per_example_loss: 15523.8 | pixel_values_sum: 1.54228E+12 | tflop_counter: 1.014E+08 | tflop_counter_no_acc: 4.055E+04 | tflops_fwd_bwd: 2.323E+03 | tflops_fwd_bwd_no_acc: 2.346E+03 | global_batch_size_current: 4096 |
** Starting validation **
Validation logs: val_per_token_loss: 3.0179 | val_per_example_loss: 14921.1 | val_num_images: 150355 | val_num_tokens: 4413196 | val_num_padding: 2292 | val_image_to_text_ratio: 0.0341 |
** Finished validation **
srun: error: Node failure on jean-zay-iam37
srun: Job step aborted: Waiting up to 62 seconds for job step to finish.
slurmstepd: error: *** STEP 1943824.0 ON jean-zay-iam17 CANCELLED AT 2023-03-06T03:17:51 DUE TO NODE FAILURE, SEE SLURMCTLD LOG FOR DETAILS ***

```
