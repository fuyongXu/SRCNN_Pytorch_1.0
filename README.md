# SRCNN

This repository is implementation of the ["Image Super-Resolution Using Deep Convolutional Networks"](https://arxiv.org/abs/1501.00092)(SRCNN)by PyTorch.

![](assets/markdown-img-paste-20190716211816899.png)


## Requirements

- PyTorch 1.0.0
- Numpy 1.15.4
- Pillow 5.4.1
- h5py 2.8.0
- tqdm 4.30.0

## Train

The 91-image, Set5 dataset converted to HDF5 can be downloaded from the links below.


Otherwise, you can use `prepare.py` to create custom dataset.

```bash
python train.py --train-file "path_to_train_file" \
                --eval-file "path_to_eval_file" \
                --outputs-dir "path_to_outputs_file" \
                --scale 3 \
                --lr 1e-4 \
                --batch-size 16 \
                --num-epochs 400 \
                --num-workers 0 \
                --seed 123                
```

## Test


```bash
python test.py --weights-file "path_to_pth_file" \
               --image-file "path_to_test_image_file" \
               --scale 3
```

## Results

We used the network settings for experiments, i.e., <a href="https://www.codecogs.com/eqnedit.php?latex={&space;f&space;}_{&space;1&space;}=9,{&space;f&space;}_{&space;2&space;}=5,{&space;f&space;}_{&space;3&space;}=5,{&space;n&space;}_{&space;1&space;}=64,{&space;n&space;}_{&space;2&space;}=32,{&space;n&space;}_{&space;3&space;}=1" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{&space;f&space;}_{&space;1&space;}=9,{&space;f&space;}_{&space;2&space;}=5,{&space;f&space;}_{&space;3&space;}=5,{&space;n&space;}_{&space;1&space;}=64,{&space;n&space;}_{&space;2&space;}=32,{&space;n&space;}_{&space;3&space;}=1" title="{ f }_{ 1 }=9,{ f }_{ 2 }=5,{ f }_{ 3 }=5,{ n }_{ 1 }=64,{ n }_{ 2 }=32,{ n }_{ 3 }=1" /></a>.

PSNR was calculated on the Y channel.
