# Semantic Segmentation Competition

This repository contains code and results for a semantic segmentation competition using a small autonomous driving dataset. The project explores various data augmentation, network architectures, and training strategies to improve segmentation accuracy and efficiency.


## Dataset

- **Training images:** 150
- **Testing images:** 50
- **Classes:** 19 (see `seg_data/names.txt`)
- **Color palette:** see `seg_data/colors.txt`

## Features

- PyTorch-based data loading and augmentation
- Custom semantic segmentation network with options for BatchNorm, Residual, Dropout, etc.
- Multiple data augmentation strategies (flip, color jitter, crop, rotation, blur, etc.)
- Training and evaluation scripts with mIoU metric
- FLOPs calculation for model efficiency
- Ablation study and results tracking

## Usage

1. **Setup**
   - Install dependencies (PyTorch, torchvision, numpy, PIL, etc.)
   - (Optional) Use Google Colab or **Kaggle** for GPU acceleration

2. **Prepare Data**
   - Place the dataset in the `seg_data/` directory as described above.

3. **Run Experiments**
   - Open and run `segmentation-2025.ipynb` or any notebook in the `result/` subfolders for specific experiments.
   - Modify data augmentation, network architecture, and training parameters as needed.

4. **Evaluate**
   - Evaluation is performed using mean Intersection over Union (mIoU).
   - Results and predictions are saved in the `result/` subfolders.

5. **Report**
   - See `Final_Report.pdf` for a summary of methods, results, and ablation studies.

## Example: Running the Baseline

Open [segmentation-2025.ipynb](segmentation-2025.ipynb) and run all cells to train and evaluate the baseline model.

## Results

- Baseline mIoU: ~0.28
- Best mIoU (with augmentation and advanced architecture): see ablation tables in the report and notebooks

## References

- [PyTorch Documentation](https://pytorch.org/docs/stable/index.html)
- [fvcore FLOPs Analysis](https://github.com/facebookresearch/fvcore)

---

**Authors:**  
Ge Wang, Tien


For more details, see the code and [Final_Report.pdf](Final_Report.pdf).