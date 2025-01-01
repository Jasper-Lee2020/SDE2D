# SDE2D
The official code of SDE2D

## Introduction
Date of Publication: 
23 December 2024.

## Dependencies
* Python 3 >= 3.5
* PyTorch >= 1.1
* OpenCV >= 3.4 
* Matplotlib >= 3.1
* NumPy >= 1.18

## SDE2D Evaluation
### Download datasets for evaluation
+ [MSVD](https://www.cs.utexas.edu/users/ml/clamp/videoDescription/) <br>
+ [MSRVTT](https://cove.thecvf.com/datasets/839) <br>

### Reproducing the evaluation on ScanNet dataset
<details>
  <summary>[Click to expand]</summary>

We provide the groundtruth for ScanNet in our format in the file `assets/scannet_test_pairs_with_gt.txt` for convenience. In order to reproduce similar tables to what was in the paper, you will need to download the dataset (we do not provide the raw test images). To download the ScanNet dataset, do the following:

1. Head to the [ScanNet](https://github.com/ScanNet/ScanNet) github repo to download the ScanNet test set (100 scenes).
2. You will need to extract the raw sensor data from the 100 `.sens` files in each scene in the test set using the [SensReader](https://github.com/ScanNet/ScanNet/tree/master/SensReader) tool.

Once the ScanNet dataset is downloaded in `~/data/scannet`, you can run the following:

```sh
./match_pairs.py --input_dir ~/data/scannet --input_pairs assets/scannet_test_pairs_with_gt.txt --output_dir dump_scannet_test_results --eval
```

You should get the following table for ScanNet (or something very close to it, see this [note](#a-note-on-reproducibility)):

```txt
Evaluation Results (mean over 1500 pairs):
AUC@5    AUC@10  AUC@20  Prec    
11.12    23.16   36.91   50.88
```

</details>

### Reproducing the evaluation on 7-Scenes dataset

### Reproducing the evaluation on HPatches dataset

## BibTeX Citation
If you use any ideas from the paper or code from this repo, please consider citing:

<!-- ```txt
@ARTICLE{10812856,

  author={Li, Jiapeng and Zhang, Ruonan and Li, Ge and Li, Thomas H.},

  journal={IEEE Transactions on Multimedia}, 

  title={SDE2D: Semantic-guided Discriminability Enhancement Feature Detector and Descriptor}, 

  year={2024},

  volume={},

  number={},

  pages={1-12},

  doi={10.1109/TMM.2024.3521748}} -->
