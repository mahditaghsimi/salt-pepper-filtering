# salt-pepper-filtering
A simple Python project demonstrating salt‑and‑pepper noise generation and basic spatial filters (Median, Min, Max) implemented from scratch using NumPy.

---

# Salt & Pepper Noise Filtering (Median, Min, Max Filters)

This project demonstrates how to add **Salt & Pepper noise** to a grayscale image and then remove the noise using three classical spatial filters:

- Median Filter (3×3)
- Min Filter (3×3)
- Max Filter (3×3)

It is implemented entirely in Python using `NumPy`, `Pillow`, and `Matplotlib`.  
The code is written to be simple, readable, and suitable for educational use.

---

<img width="328" height="350" alt="image" src="https://github.com/user-attachments/assets/6e71420c-48c4-4ac6-ae00-974e5fc82081" />

We work with the standard grayscale **Lena** image.
  
---

## 2. Adding Salt & Pepper Noise

Salt & Pepper noise is a type of impulse noise where random pixels are turned either fully white (255) or fully black (0).  
The project includes:

- A custom function `add_salt_pepper_noise(image, amount=0.05)`
- Adjustable noise density

The example uses `amount=0.05`, meaning 5% of all pixels are replaced with salt or pepper values.
  
<img width="415" height="350" alt="image" src="https://github.com/user-attachments/assets/6431fe0b-5235-41ba-8423-27fabd593c61" />


---

## 3. Replicate Padding

To correctly apply filters near image boundaries, we use a custom padding function:

`replicate_pad(image, pad=1)`

Instead of zero padding, the border pixels are **replicated outward**, producing visually smooth edges and more accurate filtering.
<img width="328" height="350" alt="image" src="https://github.com/user-attachments/assets/aa65972a-7ed2-49dc-a321-7129dc81000b" />

---

## 4. Implemented Filters

### 4.1 Median Filter (3×3)
A nonlinear filter that replaces each pixel with the median of its 3×3 neighborhood.  
This filter is especially effective for removing Salt & Pepper noise.

### 4.2 Min Filter (3×3)
A morphological erosion-like filter.  
Useful for removing **salt** (white) noise, but can darken the image.

### 4.3 Max Filter (3×3)
A morphological dilation-like filter.  
Useful for removing **pepper** (black) noise, but can brighten the image.

---

## 5. Filtering Results

Below are the outputs of each filter applied to the noisy image.

<img width="328" height="350" alt="image" src="https://github.com/user-attachments/assets/40de4c0f-08b7-417d-b375-662de51cd379" />


<img width="328" height="350" alt="image" src="https://github.com/user-attachments/assets/0770786d-45ad-402c-942f-21cbcbe0228c" />


<img width="328" height="350" alt="image" src="https://github.com/user-attachments/assets/3903f136-2cfd-410a-9fcf-04b7b6a057d4" />


---

## 6. Comparison (Side-by-Side)

A combined figure showing all three filters helps compare their performance.

<img width="1174" height="407" alt="image" src="https://github.com/user-attachments/assets/7c4cc275-3d8c-4826-898c-e7cdd1bcc9d4" />


Interpretation:

- **Median Filter**: Best at removing Salt & Pepper noise while preserving edges.
- **Max Filter**: Removes black noise (pepper) but can brighten edges.
- **Min Filter**: Removes white noise (salt) but can darken the image.

---

## 7. How to Run in Google Colab

1. Upload `Lena.png` to Colab  
2. Run the notebook cell-by-cell  
3. All results will be displayed automatically  

---

## 8. Summary

This project provides:

- A clean implementation of Salt & Pepper noise generation  
- Custom replicate padding  
- Median, Min, and Max filtering from scratch  
- Visualization of results for comparison  

It is a good reference for anyone studying **image processing**, **noise removal**, and **nonlinear filters**.


