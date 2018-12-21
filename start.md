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
```bash
pip install -r requirements.txt
python -m pip installnumpy scipy matplotlib ipython jupyter pandas sympy nose
```

### add path
```python
import sys
sys.path.append('/home/yuhuang/github/lanenet-lane-detection/')
```

### test
```bash
python tools/test_lanenet.py --is_batch False --batch_size 1 --weights_path models/new_tusimple/tusimple_lanenet_vgg_2018-10-19-13-33-56.ckpt-200000 --image_path data/tusimple_test_image/0.jpg
```




