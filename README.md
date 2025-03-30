# Neural Style Transfer

This project implements Neural Style Transfer using a pre-trained VGG-19 model. It takes a content image and a style image and generates a new image that blends the content with the artistic style.

## What is Neural Style Transfer?
Neural Style Transfer (NST) is a deep learning technique that applies the artistic style of one image to the content of another. It works by extracting the features of both images using a convolutional neural network (CNN) and optimizing a new image to combine the content with the style. 

## Requirements

Ensure you have the following installed:

- Python 3.x
- PyTorch
- torchvision
- Pillow
- NumPy

You can install them using:

```sh
pip install torch torchvision pillow numpy
```

## How It Works

1. **Load Images**: The content and style images are loaded and resized appropriately.
2. **Preprocess Images**: Images are converted into tensors and normalized.
3. **Extract Features**: A pre-trained VGG-19 model extracts feature maps at multiple layers.
4. **Compute Loss**:
   - Content loss measures the difference between the content image and generated image.
   - Style loss measures the difference in texture using Gram matrices.
5. **Optimize Image**: The generated image is updated iteratively to minimize the total loss.
6. **Save Output**: The final stylized image is saved as an output file.

## Usage

### Setup
Before running the script, create a folder named `png` and place your images inside it:
- Add your content image as `content.png` inside the `png` folder.
- Add your style image as `style.png` inside the `png` folder.

### Run the Script
Run the script using the following command:

```sh
python main.py
```

### Available Arguments

| Argument         | Description                   | Default Value     |
| ---------------- | ----------------------------- | ----------------- |
| `--content`      | Path to content image         | `png/content.png` |
| `--style`        | Path to style image           | `png/style.png`   |
| `--max_size`     | Max image size for processing | `400`             |
| `--total_step`   | Number of training iterations | `2000`            |
| `--log_step`     | Log loss every N steps        | `10`              |
| `--sample_step`  | Save image every N steps      | `500`             |
| `--style_weight` | Weight for style loss         | `100`             |
| `--lr`           | Learning rate                 | `0.003`           |

## Output

The generated image will be saved as `output-[step].png` at defined intervals.

## Notes

- A GPU is recommended for faster processing.
- The pre-trained VGG-19 model is downloaded automatically.
- Ensure images are in a valid format (JPG, PNG, etc.).

