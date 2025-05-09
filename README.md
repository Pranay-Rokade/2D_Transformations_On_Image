# 2D Transformations on Image

This project demonstrates the application of **2D geometric transformations** on an image using **OpenCV** inside a **Jupyter Notebook**. Each transformation showcases how an image can be manipulated using affine transformation matrices.

---

## 🧰 Technologies Used

- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Jupyter Notebook

---

## 🖼️ Image Transformations Performed

### 1️⃣ Translation  
Shifts the image from its original position along the x and y axes.

```python
translated_Matrix = np.float32([[1, 0, tx], [0, 1, ty]])
translated = cv2.warpAffine(img, translated_Matrix, (img.shape[1], img.shape[0]))
```

### 2️⃣ Rotation
Rotates the image clockwise and anti-clockwise around its center point.

```python
rotation_matrix = cv2.getRotationMatrix2D(center, angle, scale)
rotated = cv2.warpAffine(img, rotation_matrix, (img.shape[1], img.shape[0]))
```

### 3️⃣ Scaling
Resizes the image by a specific scaling factor using interpolation.

```python
scaled = cv2.resize(img, None, fx=4, fy=4, interpolation=cv2.INTER_LINEAR)
```

### 4️⃣ Shearing
Applies a distortion effect by skewing the image along x and/or y axes.

```python
shear_matrix = np.float32([[1, 0.2, 0], [0.2, 1, 0]])
sheared = cv2.warpAffine(img, shear_matrix, (cols, rows))
```

### 5️⃣ Reflection
Mirrors the image horizontally across the vertical axis.

```python
reflect_matrix = np.float32([[-1, 0, cols], [0, 1, 0]])
reflected = cv2.warpAffine(img, reflect_matrix, (cols, rows))
```

## 📷 Output Overview

| Transformation           | Description                         |
|--------------------------|-------------------------------------|
| Original Image           | RGB rendered image                  |
| Translation              | Image shifted by (tx, ty)           |
| Clockwise Rotation       | Rotated by +60°                     |
| Anti-clockwise Rotation  | Rotated by -60°                     |
| Translation + Rotation   | Combined transformation             |
| Scaling                  | Image scaled by factor (e.g. 4x)    |
| Shearing                 | Skewed transformation               |
| Reflection               | Horizontally flipped image          |
