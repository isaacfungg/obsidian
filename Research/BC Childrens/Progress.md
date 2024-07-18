***
```python
# Activate the unext Conda environment
conda activate unext
srun --account=st-ilker-1-gpu --partition=gpu --time=5:0:0 -N 1 -n 2 --mem=32G --gpus=4 --pty /bin/bash -c \

# Run the training with Learning Rate: 0.001, Weight Decay: 1e-4
python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.001_wd_1e-4_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-4

# Run the training with Learning Rate: 0.001, Weight Decay: 1e-5
python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.001_wd_1e-5_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-5

# Run the training with Learning Rate: 0.0001, Weight Decay: 1e-4
python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.0001_wd_1e-4_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.0001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-4

# Run the training with Learning Rate: 0.0001, Weight Decay: 1e-5
python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.0001_wd_1e-5_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.0001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-5

# Run the training with Learning Rate: 0.00001, Weight Decay: 1e-4
python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.00001_wd_1e-4_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.00001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-4

# Run the training with Learning Rate: 0.00001, Weight Decay: 1e-5
python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.00001_wd_1e-5_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.00001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-5

```