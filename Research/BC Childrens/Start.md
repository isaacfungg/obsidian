
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


