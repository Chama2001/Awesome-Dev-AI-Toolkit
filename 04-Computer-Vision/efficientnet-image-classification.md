# 👁️ EfficientNet Image Classification

EfficientNetB0 is a highly optimized architecture, making it excellent for tasks requiring high accuracy with lower computational power, such as diagnostic tools and medical imaging applications.

## 1. Install Dependencies
Make sure you have TensorFlow and Pillow installed:
```bash
pip install tensorflow numpy pillow
```

## 2. Load Model and Predict
Here is a basic script to load a pre-trained EfficientNetB0 model and classify an image:

```python
import tensorflow as tf
from tensorflow.keras.applications.efficientnet import EfficientNetB0, preprocess_input, decode_predictions
from tensorflow.keras.preprocessing import image
import numpy as np

# Load the pre-trained EfficientNetB0 model
model = EfficientNetB0(weights='imagenet')

# Load and preprocess the image (Requires a 224x224 input)
img_path = 'sample_image.jpg' # Replace with your image path
img = image.load_img(img_path, target_size=(224, 224))
x = image.img_to_array(img)
x = np.expand_dims(x, axis=0)
x = preprocess_input(x)

# Make predictions
preds = model.predict(x)
print("Predicted:", decode_predictions(preds, top=3)[0])
```
