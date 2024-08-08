
#### Training Models
1. ssh ifung01@sockeye.arc.ubc.ca
2. cd /scratch/st-ilker-1/ifung01/UNeXt-pytorch
3. conda activate unext
4. python ...

#### Reusing models
cd Unext/models
python val.py --name experiment_test_20_epochs
#### Location of Data
cd /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset
#### Checking the images
cd /scratch/st-ilker-1/ifung01/UNeXt-pytorch/outputs
#### Batch Jobs
sbatch test_batch_jobs.sh
squeue -u ifung01
#### File Manager
https://app.globus.org/file-manager/collections
Look in collection "ubcarc#sockeye"
#### example run code
srun --account=st-ilker-1-gpu --partition=gpu --time=2:0:0 -N 1 -n 2 --mem=32G --gpus=4 --pty bash -c "python train.py --dataset /scratch/st-ilker-1/ifung01/US_Children_dataset_segmentation/full_dataset \

batch13.sh
...
batch22.sh
batch23.sh
batch24.sh
batch25.sh
batch26.sh
batch27.sh
batch28.sh
batch29.sh
batch30.sh
batch31.sh
batch32.sh
batch33.sh
batch34.sh
batch35.sh
