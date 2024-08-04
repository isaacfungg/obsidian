1. VPN
2. cd UNeXt-pytorch
3. module load miniconda3
4. source /arc/software/spack-2024/opt/spack/linux-rocky9-skylake_avx512/gcc-9.4.0/miniconda3-4.9.2-i27tct3b7z5gwpnz6b5y3dfviowrjv4o/etc/profile.d/conda.sh
5. conda activate unext
6. python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name experiment_1 --img_ext .png --mask_ext .png --lr 0.0001 --epochs 500 --input_w 512 --input_h 512 --b 8

#### Training Models
1. ssh ifung01@sockeye.arc.ubc.ca
2. cd /scratch/st-ilker-1/ifung01/UNeXt-pytorch
3. conda activate unext
4. python ...

#### Reusing models
cd Unext/models
python val.py --name experiment_test_20_epochs


#### Checking the images
cd /scratch/st-ilker-1/ifung01/UNeXt-pytorch/outputs

#### File Manager
https://app.globus.org/file-manager/collections
Look in collection "ubcarc#sockeye"

#### example run code
srun --account=st-ilker-1-gpu --partition=gpu --time=2:0:0 -N 1 -n 2 --mem=32G --gpus=4 --pty bash -c "python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \