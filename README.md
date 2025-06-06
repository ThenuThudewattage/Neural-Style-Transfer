# Neural Style Transfer

## Requirements

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


### Setup
Before running the script, create a folder named `png` and place your images inside it:
- Add your content image as `content.png` inside the `png` folder.
- Add your style image as `style.png` inside the `png` folder.

### Run the Script
Run the script using the following command:

```sh
python main.py
```


## Notes

- A GPU is recommended for faster processing.
- The pre-trained VGG-19 model is downloaded automatically.
- Ensure images are in a valid format (JPG, PNG, etc.).

