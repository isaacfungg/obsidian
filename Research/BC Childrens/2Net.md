***
#### Running Code
python train.py --root_path ./data/Synapse/train_npz --test_path ./data/Synapse/test_vol_h5 --batch_size 20 --eval_interval 20 --max_epochs 700


#### Testing Model
python test.py --volume_path ./data/Synapse/ --output_dir ./model_out