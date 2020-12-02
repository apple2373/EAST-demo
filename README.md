# EAST-demo

- This is copied and modified from https://github.com/argman/EAST
- No training code included in this repository. 
- This is just to run inference based on a trained model with the original resolution of 512x512 cropped images.
- I just wanted to show a proof-of-concept to demonstrate the merit of high-resolution images for character detection. 
- see [samples](./data/outputs-demo/show.md)
- The below is how to use the model. 

# Requirements
- Python 3. I'm using Python 3.6.5. 
- Any tensorflow version  1.x should be ok. I'm using 1.9.0. 
- You can check `env.yml` to see the exact environment I'm using. 
- You could do the following to create the env for this. 
```
conda deactivate
conda create  -y  --prefix=conda python=3.6.5
conda activate ./conda
conda env update -f env.yml
```

# Install 
You need to complile `geo_map_cython_lib` and `lanms`
```
cd ./geo_map_cython_lib
bash build_ext.sh
```
and
```
cd ./lanms
make
```
- note: I had to upgrade gcc to version 6 or higher. I used gcc 8.3 and worked.

# Restore Weights
```
cd ./data
cat weights.zip.* >> weights.zip
unzip weights.zip
```

# Run
I've included demo images from kokumin, and models trained wituhout kokumin. Here's a command to use. 
```
python demo.py --test_data_path=./data/kokumin_subset --resume=./data/weights/model.ckpt-9091 -output_dir=./data/outputs/  --gpu_list=0  --max_side_len 3200
```
