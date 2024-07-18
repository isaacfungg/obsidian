1. VPN
2. cd UNeXt-pytorch
3. module load miniconda3
4. source /arc/software/spack-2024/opt/spack/linux-rocky9-skylake_avx512/gcc-9.4.0/miniconda3-4.9.2-i27tct3b7z5gwpnz6b5y3dfviowrjv4o/etc/profile.d/conda.sh
5. conda activate unext
6. python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset --arch UNext --name experiment_1 --img_ext .png --mask_ext .png --lr 0.0001 --epochs 500 --input_w 512 --input_h 512 --b 8
