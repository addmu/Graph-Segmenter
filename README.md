## Graph-Segmenter: Graph Transformer with Boundary-aware Attention for Semantic Segmentation


<p align="center">
    <img src="intro.jpg" width=800>
</p>


## Get start

### Installation

Please refer to [get_started.md](https://github.com/open-mmlab/mmsegmentation/blob/v0.11.0/docs/get_started.md#installation) for installation and dataset preparation.

### Inference
```
# single-gpu testing
python tools/test.py <CONFIG_FILE> <SEG_CHECKPOINT_FILE> --eval mIoU

# multi-gpu testing
tools/dist_test.sh <CONFIG_FILE> <SEG_CHECKPOINT_FILE> <GPU_NUM> --eval mIoU

# multi-gpu, multi-scale testing
tools/dist_test.sh <CONFIG_FILE> <SEG_CHECKPOINT_FILE> <GPU_NUM> --aug-test --eval mIoU
```

### Training

To train with pre-trained models, run:
```
# single-gpu training
python tools/train.py <CONFIG_FILE> --options model.pretrained=<PRETRAIN_MODEL> [model.backbone.use_checkpoint=True] [other optional arguments]

# multi-gpu training
tools/dist_train.sh <CONFIG_FILE> <GPU_NUM> --options model.pretrained=<PRETRAIN_MODEL> [model.backbone.use_checkpoint=True] [other optional arguments] 
```
For example, to train an UPerNet model with a `Swin-T` backbone and 8 gpus, run:
```
tools/dist_train.sh configs/swin/upernet_swin_tiny_patch4_window7_512x512_160k_ade20k.py 8 --options model.pretrained=<PRETRAIN_MODEL> 
```

## Citing Graph-Segmenter
```
@article{liu2021Swin,
  title={Graph-Segmenter: Graph Transformer with Boundary-aware Attention for Semantic Segmentation},
  author={Zizhang Wu and Jun Li and Yuanzhu Gan and Muqing Fang and Tianhao Xu and Fan Wang},
  year={2022}
}
