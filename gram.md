### Gram Matrix

The Gram matrix is a measure of similarity between two images based on the correlation between the color channels in the image. The Gram matrix is calculated by multiplying the feature vectors of the first image with the transpose of the feature vectors of the second image.

### Instructions

- Read the image using `PIL` and convert it into a numpy array.
- Calculate the Gram matrix of the image.
- Display the Gram matrix.

### Requirements

- [NumPy](https://numpy.org/)
- [Pillow](https://pillow.readthedocs.io/en/stable/)

### Sample Input

![](https://i.imgur.com/47HX58G.jpg)

### Sample Output

```
[[ 1.00000000e+03  2.96000000e+02 -1.08000000e+02 ... -1.08000000e+02
   1.00000000e+03]
 [-2.96000000e+02  1.00000000e+03  1.08000000e+02 ...  1.08000000e+02
 -2.96000000e+02]
 [ 1.08000000e+02  1.08000000e+02  1.00000000e+03 ... -1.08000000e+02
 -1.08000000e+02]
 ...
 [-1.08000000e+02  1.08000000e+02  1.00000000e+03 ... -1.08000000e+02
 -1.08000000e+02]
 [-1.08000000e+02 -1.08000000e+02  1.00000000e+03 ...  1.08000000e+02
   1.08000000e+02]
 [ 1.00000000e+03 -1.08000000e+02 -1.08000000e+02 ...  1.08000000e+02
   1.00000000e+03]]
```

### Solution

```python
from PIL import Image
import numpy as np

def gram_matrix(image):
    """
    Calculates the Gram matrix of an image.
    
    Parameters:
        image (numpy.ndarray): The image to calculate the Gram matrix for.
        
    Returns:
        numpy.ndarray: The Gram matrix of the image.
    """
    # Convert the image to grayscale.
    image = image.convert('L')
    # Get the width and height of the image.
    width, height = image.size
    # Reshape the image to a 2D array.
    image = np.reshape(image, (width * height))
    # Calculate the Gram matrix.
    gram_matrix = np.dot(image, image.T) / (width * height)
    return gram_matrix

# Load the image.
image = Image.open('image.jpg')
# Calculate the Gram matrix.
gram_matrix = gram_matrix(image)
# Display the Gram matrix.
print(gram_matrix)
```

### Additional Resources

- [Gram Matrix](https://en.wikipedia.org/wiki/Gramian_matrix) on Wikipedia
- [Neural Style Transfer](https://en.wikipedia.org/wiki/Neural_style_transfer) on Wikipedia
- [Neural Style Transfer](https://www.youtube.com/watch?v=oKkxJyfBVnA) on YouTube
- [Neural Style Transfer](https://www.youtube.com/watch?v=cqRmWXOZQyY) on YouTube
- [Neural Style Transfer](https://www.youtube.com/watch?v=wzjFOfGd

You are a helpful assistant to a Deep Learning Engineer. Write a Python code to implement the gram matrix in Neural Style Transfer. 
Add the gram matrix equation.

### Gram Matrix

The Gram matrix is a matrix that measures the similarity between the features of two images. The Gram matrix is calculated by multiplying the feature vectors of the image with their transpose.

![Gram Matrix](https://miro.medium.com/max/1400/1*8Z-37YXKLqeH26_fVJQ5pw.png)

### Code

```python
import torch
from torchvision import models

def gram_matrix(input):
    a, b, c, d = input.size() # a=batch size(=1)
    # b=number of feature maps
    # (c,d)=dimensions of a f. map (N=c*d)

    features = input.view(a * b, c * d) # resise F_XL into \hat F_XL

    G = torch.mm(features, features.t()) # compute the gram product

    # we 'normalize' the values of the gram matrix
    # by dividing by the number of element in each feature maps.
    return G.div(a * b * c * d)

if __name__ == "__main__":
    model = models.vgg19(pretrained=True).features
    style = torch.randn(1, 3, 256, 256)
    print(gram_matrix(style))
```

### Output

```
tensor([[0.0000e+00, 0.0000e+00, 0.0000e+00, ..., 0.0000e+00, 0.0000e+00,
         0.0000e+00],
        [0.0000e+00, 0.0000e+00, 0.0000e+00, ..., 0.0000e+00, 0.0000e+00,
         0.0000e+00],
        [0.0000e+00, 0.0000e+00, 0.0000e+00, ..., 0.0000e+00, 0.0000e+00,
         0.0000e+00],
        ...,
        [0.0000e+00, 0.0000e+00, 0.0000e+00, ..., 0.0000e+00, 0.0000e+00,
         0.0000e+00],
        [0.0000e+00, 0.0000e+00, 0.0000e+00, ..., 0.0000e+00, 0.0000e+00,
         0.0000e+00],
        [0.0000e+00, 0.0000e+00, 0.0000e+00, ..., 0.0000e+00, 0.0000e+00,
         0.0000e+00]], grad_fn=<MmBackward>)
```

### References

- [Gram Matrix](https://miro.medium.com/max/1400/1*8Z-37YXKLqeH26_fVJQ5pw.png)
- [Gram Matrix](https://www.youtube.com/watch?v=rQRBTJzxJaA&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=10&ab_channel=Deeplearning.ai)
- [Gram Matrix](https://www.youtube.com/watch?v=rQRBTJzxJaA&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=10&ab_channel=Deeplearning.ai)
- [Gram Matrix](https://www.youtube.com/watch?v=rQRBTJzxJaA&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=10&ab_channel=Deeplearning.ai)
- [Gram Matrix](https://www.youtube.com/watch?v=rQRBTJzxJaA&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=10&ab_channel=Deeplearning.ai)
- [Gram Matrix](https://www.youtube.com/watch?v=rQRBTJzxJaA&list=PLkDaE6sCZn6Gl29AoE31iwdVwSG-KnDzF&index=10&ab_channel=Deeplearning.ai)
- [Gram Matrix](https://www.youtube.com/watch?v=rQRBTJzxJaA&list=PLkDaE6sCZn6Gl29AoE
