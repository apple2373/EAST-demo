The model is trained from
```
python multigpu_train.py --training_data_path=../data/east_char_train --geometry=RBOX --pretrained_model_path=./resnet_v1_50.ckpt --learning_rate=0.0001 --input_size=512 --text_scale=512 --num_readers=24 --checkpoint_path=./experiments/east-char-crop/ --min_text_size 10 --batch_size_per_gpu 14 --gpu_list=2 --prep crop --cls_loss_scale 0.1
```
under `/u/stsutsui/tynamo/book-layout/EAST` at tynamo one. 


- test_scale means "scaling factor for  geo_map. max size of geo_map. the geomap will be between 0 to text_scale" where geo_map is (probably:L) label tensor (kind of segmentation map but this one is not just binary seg, see paper:).  
- min_text_size was also important so that it will not find noise as text? maybe? 
