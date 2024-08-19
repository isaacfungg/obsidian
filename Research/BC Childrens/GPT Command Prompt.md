***
Single Validation Comand
srun --account=st-ilker-1-gpu --partition=gpu --time=0:15:0 -N 1 -n 2 --mem=32G --gpus=4 --pty bash -c "python val.py --name lr_0.0005_epochs_20_wd_5e-5_gamma_0.9"

Single Train Command - For training make sure there is 1 hour for every 50 epoch
srun --account=st-ilker-1-gpu --partition=gpu --time=8:00:0 -N 1 -n 2 --mem=32G --gpus=4 --pty bash -c "python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name lr_0.005_epoch_75_wd_5e-5_gamma_0.9 --img_ext .png --mask_ext .png --lr 0.005 --epochs 75 --weight_decay 5e-5 --gamma 0.9 --input_w 512 --input_h 512 --batch_size 32 --num_classes 2"

Batch
```shell
#!/bin/bash

#SBATCH --account=st-ilker-1-gpu

#SBATCH --partition=gpu

#SBATCH --time=12:00:0

#SBATCH -N 1

#SBATCH -n 2

#SBATCH --mem=32G

#SBATCH --gpus=4

  

module load miniconda3/4.9.2

  

# Change directory and activate conda environment

cd /scratch/st-ilker-1/ifung01/UNeXt-pytorch

source /arc/software/spack-2024/opt/spack/linux-rocky9-skylake_avx512/gcc-9.4.0/miniconda3-4.9.2-i27tct3b7z5gwpnz6b5y3dfviowrjv4o/etc/profile.d/conda.sh

conda activate unext

  

# Test Job 1: lr=0.005, weight_decay=5e-5, gamma=1.0

srun python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name lr_0.005_epoch_75_wd_5e-5_gamma_1.0 --img_ext .png --mask_ext .png --lr 0.005 --epochs 75 --weight_decay 5e-5 --gamma 1.0 --input_w 512 --input_h 512 --batch_size 32 --num_classes 2

srun python val.py --name lr_0.005_epoch_75_wd_5e-5_gamma_1.0

  

# Test Job 2: lr=0.004, weight_decay=5e-5, gamma=1.0

srun python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name lr_0.004_epoch_75_wd_5e-5_gamma_1.0 --img_ext .png --mask_ext .png --lr 0.004 --epochs 75 --weight_decay 5e-5 --gamma 1.0 --input_w 512 --input_h 512 --batch_size 32 --num_classes 2

srun python val.py --name lr_0.004_epoch_75_wd_5e-5_gamma_1.0

  

# Test Job 3: lr=0.003, weight_decay=1e-4, gamma=1.0

srun python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name lr_0.003_epoch_75_wd_1e-4_gamma_1.0 --img_ext .png --mask_ext .png --lr 0.003 --epochs 75 --weight_decay 1e-4 --gamma 1.0 --input_w 512 --input_h 512 --batch_size 32 --num_classes 2

srun python val.py --name lr_0.003_epoch_75_wd_1e-4_gamma_1.0

  

# Test Job 4: lr=0.004, weight_decay=1e-4, gamma=0.8

srun python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name lr_0.004_epoch_75_wd_1e-4_gamma_0.8 --img_ext .png --mask_ext .png --lr 0.004 --epochs 75 --weight_decay 1e-4 --gamma 0.8 --input_w 512 --input_h 512 --batch_size 32 --num_classes 2

srun python val.py --name lr_0.004_epoch_75_wd_1e-4_gamma_0.8

  

# Test Job 5: lr=0.005, weight_decay=5e-5, gamma=0.9

srun python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name lr_0.005_epoch_75_wd_5e-5_gamma_0.9 --img_ext .png --mask_ext .png --lr 0.005 --epochs 75 --weight_decay 5e-5 --gamma 0.9 --input_w 512 --input_h 512 --batch_size 32 --num_classes 2

srun python val.py --name lr_0.005_epoch_75_wd_5e-5_gamma_0.9
```