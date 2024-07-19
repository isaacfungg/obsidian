***
#### Learning Rate: 0.001, Weight Decay: 1e-5, Gamma: 0.5, Epoch: 50
Name: **exp_lr_0.001_wd_1e-5_gamma_0.5_epochs_50**

###### Train:
Loss: 0.5194
IoU: 0.3824 
val_loss: 0.5150 
val_iou: 0.3882
###### Test:
IoU: 0.3882
Dice: 0.5593

#### Learning Rate: 0.001, Weight Decay: 1e-5, Gamma: 0.7, Epoch: 50
Name: **exp_lr_0.001_wd_1e-5_gamma_0.7_epochs_50**
###### Train:
Loss: 0.3169
IoU: 0.4248 
val_loss: 0.3147
val_iou: 0.4294
###### Test:
IoU: 0.4252
Dice: 0.5967

#### Learning Rate: 0.001, Weight Decay: 1e-4, Gamma: 0.5, Epoch: 50
Name: **exp_lr_0.001_wd_1e-4_gamma_0.5_epochs_50**
###### Train:
Loss: 0.3629
IoU: 0.3971
val_loss: 0.3511
val_iou: 0.4081

###### Test:
IoU: 0.4152
Dice: 0.5867

```python
python train.py --dataset /scratch/st-ilker 1/ifung01/US_Children_dataset_segmentation/full_dataset \
                --arch UNext --name exp_lr_0.001_wd_1e-4_epochs_100 --img_ext .png --mask_ext .png \
                --lr 0.001 --epochs 100 --input_w 512 --input_h 512 -b 64 --weight_decay 1e-4

```

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