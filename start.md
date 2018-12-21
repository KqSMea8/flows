## Install tensorflow and libs

### create venv for tensorflow
```bash
python3 -m virtualvenv ~/tensorflowvenv
```

### get the repo
```bash
cd ~/whitebase
git clone https://github.com/yyuuliang/flows.git
```

### install  
We have to install tensorflow's nightly build version as this is the only way to get CUDA-10 support currently. The stable version with CUDA-10 support will be released next month  
```bash
pip install -r requirements.txt
```

### lane-net
git   
https://github.com/MaybeShewill-CV/lanenet-lane-detection  
new models  
https://www.dropbox.com/sh/tnsf0lw6psszvy4/AAA81r53jpUI3wLsRW6TiPCya?dl=0 


## check gpu support
```bash
from tensorflow.python.client import device_lib 
print(device_lib.list_local_devices())
 ```
### add path to test.py and train.py
```python
import sys
sys.path.append('/home/yuhuang/github/lanenet-lane-detection/')
```

### test
```bash
# single pic
python tools/test_lanenet.py --is_batch False --batch_size 1 --weights_path models/new_tusimple/tusimple_lanenet_vgg_2018-10-19-13-33-56.ckpt-200000 --image_path data/tusimple_test_image/0.jpg
# batch pic
python tools/test_lanenet.py --is_batch True --batch_size 2 --save_dir data/tusimple_test_image/ret  --weights_path models/new_tusimple/tusimple_lanenet_vgg_2018-10-19-13-33-56.ckpt-200000 --image_path data/tusimple_test_image/
```


### train
download the vgg16.npy  
https://github.com/machrisaa/tensorflow-vgg
change the PATH in data/training_data_example/train.txt and val.txt  
change batch_size to 1 in /config/global_config.py

### train script
```bash
python tools/train_lanenet.py --net vgg --dataset_dir data/training_data_example/
```

