# Semantic Segmentation Competition

This repository contains code and results for a semantic segmentation competition using a small autonomous driving dataset. The project explores various data augmentation strategies, network architectures, and training techniques to improve segmentation accuracy and efficiency on urban road scenes.

## Dataset

- **Training images:** 150
- **Testing images:** 50
- **Classes:** 19 (see `seg_data/names.txt`)
- **Color palette:** see `seg_data/colors.txt`

## Installation

```bash
pip install -r requirements.txt
```

## Project Structure

```
.
├── segmentation-2025.ipynb          # Main notebook (all experiments consolidated)
├── requirements.txt                  # Python dependencies
├── Final_Report.pdf                  # Detailed report with ablation studies
├── seg_data/
│   ├── training/image/               # Training images
│   ├── training/label/               # Training labels
│   ├── testing/                      # Testing images
│   ├── names.txt                     # Class names
│   └── colors.txt                    # Class color palette
└── result/
    ├── baseline/                     # Baseline model
    ├── flip_augmentation/            # Flip augmentation experiment
    ├── flip_colorjitter_batchnorm/   # Flip + color jitter + batch normalization
    ├── baseline_augmentation/        # Baseline with data augmentation
    ├── residual_skip_dilated_augmentation/  # Residual + skip + dilated convolutions
    ├── mobilenetv3_crossentropy/     # MobileNetV3 with cross-entropy loss
    ├── mobilenetv3_hybrid_loss/      # MobileNetV3 with hybrid (CE + Dice) loss
    ├── mobilenetv3_augmentation_crossentropy/  # MobileNetV3 + augmentation + CE loss
    ├── crop_rot_blur_jitter_hybrid_loss/  # Crop + rotation + blur + jitter + hybrid loss
    └── crop_rot_blur_jitter_adamw_batchnorm_residual_skip_dilated/  # Full pipeline experiment
```

## Usage

1. **Prepare Data**
   - Place the dataset in the `seg_data/` directory following the structure above.

2. **Run Experiments**
   - Open and run `segmentation-2025.ipynb` for the main experiment pipeline.
   - Each subfolder in `result/` contains a notebook for a specific ablation study.

3. **Evaluate**
   - Evaluation uses mean Intersection over Union (mIoU) as the primary metric.
   - Results and predictions are saved in the `result/` subfolders.

## Results

- Baseline mIoU: ~0.28
- Best mIoU: see ablation tables in `Final_Report.pdf` and individual notebooks

## References

- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [fvcore FLOPs Analysis](https://github.com/facebookresearch/fvcore)
