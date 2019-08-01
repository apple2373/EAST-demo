# EAST-demo

- This is copied and modified from https://github.com/argman/EAST



# Requirements
- Python 3. I'm using Python 3.6.5. 
- Any tensorflow version  1.x should be ok. I'm using 1.9.0. 
- You can check env.yml to see the exact environment I'm using. You could do `conda env update -f env.yml` in your conda env. 

# Install 
- You will need to complile xxx

# Restore Weights
```
cd ./data
cat weights.zip.* >> weights.zip
unzip weights.zip
```

# Run
I've included demo images from kokumin, and models trained wituhout kokumin. Here's the command to use. 
```
python demo.py --test_data_path=./data/east_char_test_subset --resume=./data/weights/model.ckpt-9091 -output_dir=./data/outputs/  --gpu_list=2  --max_side_len 3200
```
