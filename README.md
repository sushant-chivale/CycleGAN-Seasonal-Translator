# CycleGAN - Summer to Winter Image Translation

PyTorch implementation of CycleGAN for converting summer scenes to winter scenes and vice versa.

## Quick Start

### Install Dependencies
```bash
pip install torch torchvision matplotlib pillow
```

### Dataset Structure
```
data/
├── trainA/    # Summer images
├── trainB/    # Winter images  
├── testA/     # Summer test images
└── testB/     # Winter test images
```

### Create Directories
```bash
mkdir -p data/{trainA,trainB,testA,testB} saved_models images/summer2winter results/{A_to_B,B_to_A}
```

### Training
```python
python your_script.py  # Run the main training code
```

### Key Parameters
- **Epochs**: 10
- **Batch Size**: 1
- **Learning Rate**: 0.0002
- **Cycle Loss Weight**: 10.0
- **Identity Loss Weight**: 5.0

## Model Architecture
- **Generator**: Encoder-Decoder with 6 ResBlocks + AdaIN
- **Discriminator**: PatchGAN architecture
- **Loss Functions**: Adversarial + Cycle Consistency + Identity

## Features
- ✅ Unpaired image translation
- ✅ Cycle consistency loss
- ✅ Identity preservation
- ✅ Noise injection during training
- ✅ Replay buffer for stable training
- ✅ Automatic model saving every 10 epochs

## Output
- Models saved to `saved_models/`
- Test results saved to `results/A_to_B/` and `results/B_to_A/`
- Training samples saved to `images/summer2winter/`

## Usage
1. Place summer images in `data/trainA/` and `data/testA/`
2. Place winter images in `data/trainB/` and `data/testB/`
3. Run the training script
4. Check results in `results/` folder after training
