# CFI-Former
Enhancing Group Activity Recognition via Cross-Feature Interaction Transformer

# Abstract
Group activity recognition (GAR) is a significant and challenging task that has attracted considerable attention in video analysis. However, most of the existing models directly integrated the outcome of feature streams in a simple manner, resulting in the inability to fully mine sufficient and complementary information among different feature branches. To this end, we propose a novel cross-feature interaction Transformer (CFI-Former) for precise group activity recognition, which can explore cross-feature complementary information. Specifically, we first perform feature rectification and filter the irrelevant information through the cross-feature rectification module. The CFI-Former, intertwining cross-attention mechanism and gated bottleneck block, can jointly capture the inter-feature correlations in an interactive manner. In addition, an asymmetric convolution fusion block is designed to implement inter-frame feature aggregation, which can effectively integrate spatial-temporal information by the horizontal and vertical kernels. A series of ablation studies are designed to highlight the relative contributions of the various parts of the proposed network. Extensive experiments conducted on three widely-adopted datasets demonstrate that our method yields excellent performance compared to the state-of-the-art (SOTA) models. 

# Learning Actor Relation Graphs for Group Activity Recognition

Source code for the following paper([arXiv link](https://arxiv.org/abs/1904.10117)):

        Learning Actor Relation Graphs for Group Activity Recognition
        Jianchao Wu, Limin Wang, Li Wang, Jie Guo, Gangshan Wu
        in CVPR 2019
        
        


## Dependencies

- Python `3.x`
- PyTorch `0.4.1`
- numpy, pickle, scikit-image
- [RoIAlign for Pytorch](https://github.com/longcw/RoIAlign.pytorch)
- Datasets: [Volleyball](https://github.com/mostafa-saad/deep-activity-rec), [Collective](http://vhosts.eecs.umich.edu/vision//activity-dataset.html)




## Prepare Datasets

1. Download [volleyball](http://vml.cs.sfu.ca/wp-content/uploads/volleyballdataset/volleyball.zip) or [collective](http://vhosts.eecs.umich.edu/vision//ActivityDataset.zip) dataset file.
2. Unzip the dataset file into `data/volleyball` or `data/collective`.




## Get Started

1. Stage1: Fine-tune the model on single frame without using GCN.

    ```shell
    # volleyball dataset
    python scripts/train_volleyball_stage1.py
    
    # collective dataset
    python scripts/train_collective_stage1.py
    ```

2. Stage2: Fix weights of the feature extraction part of network, and train the network with GCN.

    ```shell
    # volleyball dataset
    python scripts/train_volleyball_stage2.py
    
    # collective dataset
    python scripts/train_collective_stage2.py
    ```
    
    You can specify the running arguments in the python files under `scripts/` directory. The meanings of arguments can be found in `config.py`



## Citation

```
@inproceedings{CVPR2019_ARG,
  title = {Learning Actor Relation Graphs for Group Activity Recognition},
  author = {Jianchao Wu and Limin Wang and Li Wang and Jie Guo and Gangshan Wu},
  booktitle = {CVPR},
  year = {2019},
}
```
