## Our Implementation details
Add two fiels in sslime/data/ssl_transforms: ssl_jigsaw_colorization.py; ssl_jigsaw.py;
Changed files in sslime/models/trunks:
vgg_a.py
Added permutations_1000.npy and permutations_color_1000.npy for predefined permutation set.
#### Run procedures
Training without using unsupervised data:\
python3 tools/train.py --config_file extra_scripts/no_unsupervised.yaml

Training with unsupervised data: \
python3 tools/train.py --config_file extra_scripts/unsupervised_vgg_a_jigsaw_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/unsupervised_vgg_a_jigsaw_color_stl_10.yaml

Supervised finetuning:\
* Jigsaw \
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw-2_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw-3_stl_10.yaml\
* Jigsaw + Colorization \
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_color1_head_layer1_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_color1_head_layer2_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_color1_head_layer3_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_color2_head_layer1_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_color2_head_layer2_stl_10.yaml\
python3 tools/train.py --config_file extra_scripts/eval_vgg_a_jigsaw_color2_head_layer3_stl_10.yaml\
# FAIR SSLIME

## Introduction
We present Self-Supervised Learning Integrated Multi-modal Environment (SSLIME), a toolkit based on PyTorch that aims to accelerate research cycle in self-supervised learning: from designing a new self-supervised task to evaluating the learned representations. The toolkit treats multiple data modalities (images, videos, audio, text) as first class citizens. The toolkit aims to provide reference implementations of several self-supervised pretext tasks and also provides an extensive benchmark suite for evaluating self-supervised representations. The toolkit is designed to be easily reusable, extensible and enable reproducible research. The toolkit also aims to support efficient distributed training across multiple nodes to facilitate research on Facebook scale data.

<p align="center">
  <img src="demo/framework_components.png" alt="Framework Components" title="Framework Components"/>
</p>

<p align="center">
  <img src="demo/framework_features.png" alt="Framework Features" title="Framework Features"/>
</p>

Currently, the toolkit supports the Rotation [1] Pretext task and evaluation of features from different layers. Support for Jigsaw, Colorization and DeepCluster pretext tasks will be added in the coming months.

## Installation

Please find installation instructions in [`INSTALL.md`](INSTALL.md).

## Getting Started
See [`STL10.md`](STL10.md) for how to setup and run on stl 10


## License

sslime is CC-NC 4.0 International licensed, as found in the LICENSE file.

## Citation

If you use sslime in your research, please use the following BibTeX entry.

```
@article{sslime2019,
  title={SSLIME: A Toolkit for Multi-Modal Self-Supervised Training and Benchmarking},
  author={Bhooshan, Suvrat and Misra, Ishan and Fergus, Rob and Goyal, Priya},
  year={2019}
}
```

## References
- Gidaris, Spyros, Praveer Singh, and Nikos Komodakis. "Unsupervised representation learning by predicting image rotations." arXiv preprint arXiv:1803.07728 (2018).
