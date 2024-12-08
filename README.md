# PixelPlayground: A Fun Dive Into Image Processing 🚀  
![Waketime](https://img.shields.io/badge/Waketime-21%20hrs%2047%20mins-blueviolet?style=flat&labelColor=black&logo=clock&logoColor=white)

**PixelPlayground** is a student project created as part of an assignment at **IIIT Hyderabad**. It explores and experiments with **basic image processing techniques** using Python. The project aims to provide an educational experience in understanding how images are represented, manipulated, and processed, with a focus on fundamental image transformations such as convolutions, blurring, sharpening, and edge detection.

---

## Features 🌟  

### 1. **Learn Image Basics** 🖼️  
   - Learn how **images** are represented as 2D grids of pixels.  
   - Understand **RGB** and **grayscale** image representations.  
   - Explore **image resolution** and how pixels combine to form an image.

### 2. **Manipulate Images** 🔄  
   - Display the **left half** of any image.  
   - **Flip** images both **horizontally** and **vertically**.

### 3. **Image Processing Techniques** 🎨  
   - **Convolutions:** Implement basic **convolution** operations using custom kernels.  
   - **Blurring:** Apply **Gaussian Blur** to smooth images.  
   - **Sharpening:** Enhance image details using **sharpening filters**.  
   - **Edge Detection:** Use **Sobel kernels** to highlight edges in images.

---

## Getting Started 🛠️  

### Prerequisites 📥  
To run the code, you need to install the following libraries:
```bash
!pip install matplotlib opencv-python numpy
```

### How to Use 🖱️  
1. Clone or **download** the repository.  
2. Open and run the **Jupyter Notebook** (`Task 2.ipynb`).  
3. Experiment with the **prebuilt functions** and apply them to your own images.

---

## Code Highlights ✨  

### Display the Left Half of an Image 📸  
```python
def displayLeftHalf(image):
    img = cv.imread(image)
    img = cv.cvtColor(img, cv.COLOR_BGR2RGB)
    img = img[:, :img.shape[1]//2]
    plt.axis("off")
    plt.imshow(img)
    plt.show()
```

### Flip an Image 🔄  
```python
def flip_image(img, vertical=False, horizontal=False):
    if vertical:
        img = img[::-1, :, :]
    if horizontal:
        img = img[:, ::-1, :]
    return img
```

### 2D Convolution 🧠  
```python
def t2D_convolution(img, kernel):
    kernel_size = len(kernel)
    pad_img = np.pad(img, ((kernel_size//2, kernel_size//2), (kernel_size//2, kernel_size//2), (0, 0)), 'constant')
    conv_img = np.zeros_like(img)
    for i in range(img.shape[0]):
        for j in range(img.shape[1]):
            for k in range(img.shape[2]):  
                conv_img[i, j, k] = np.sum(pad_img[i:i+kernel_size, j:j+kernel_size, k] * kernel)
    return conv_img
```

---

## How It Works 🤔  

### Convolutions Explained 📚  
Convolutions are central to **image processing** and **Convolutional Neural Networks (CNNs)**. This project demonstrates **2D convolutions** by implementing them manually, helping you understand their role in image transformations.

### Custom Kernels 🛠️  
Experiment with different types of **kernels** to manipulate images:
- **Gaussian kernel** for **blurring**.
- **Laplacian kernel** for **sharpening**.
- **Sobel kernels** for **edge detection**.

---

## Visual Results 🎨  

### Blurring Example 🌫️  
Before:  
```markdown
(Displayed in notebook)
```  

After (Gaussian Blur):  
```markdown
(Displayed in notebook)
```  

### Edge Detection Example 🛠️  
Before:  
```markdown
(Displayed in notebook)
```  

After (Edge Detection):  
```markdown
(Displayed in notebook)
```  

---

## Resources 📚  
- [Better Explained: Convolution](https://betterexplained.com/articles/intuitive-convolution/)  
- [Grant Sanderson's 2D Convolutions Video](https://www.youtube.com/watch?v=8rrHTtUzyZA)  
- [Image Processing Playlist](https://www.youtube.com/playlist?list=PL2zRqk16wsdqXEMpHrc4Qnb5rA1Cylrhx)  

---

## Contributing 🤝  
Feel free to **fork** the repository and contribute by adding new features or improving existing functions. Let's collaborate and build together!

---

## Authors 🧑‍💻
- **Shreyas Mehta**
---

**Enjoy exploring image processing with PixelPlayground!** 🌈

---
