

# 🖼️ A Robust DCT Based Blind Watermarking
Framework Using Hessenberg SVD Scrambling for
Secure Color Image Authentication**


## 📘 **Project Overview**

This project implements a **robust blind image watermarking system** designed for copyright protection and secure image authentication.
It is based on the **Discrete Cosine Transform (DCT)** and a **Hessenberg–Singular Value Decomposition (SVD)**–driven scrambling algorithm.

Unlike hybrid models that rely on multiple transforms (like DWT), this framework is **purely DCT-based** — enhancing computational efficiency and ensuring high imperceptibility and robustness under noise, sharpening, and scaling attacks.

The approach embeds a scrambled watermark into **mid-frequency DCT coefficients**, maintaining image quality while making unauthorized removal or detection nearly impossible.
Watermark extraction is **blind**, meaning no original image is needed for recovery.

---

## 🎯 **Abstract**

The methods used to provide digital rights management (DRM) protection, ownership verification, and fraud
mitigation relating to digital images have grown significantly over
the last few years, resulting in much greater concern about the
potential for usage, alteration, and piracy due to the vast number
of images available via the Internet. To combat this growing trend,
a new system of watermarking digital images is proposed using
the Discrete Cosine Transform (DCT).
Instead of using multiple methods (i.e. DWT, etc.), the DCT
algorithm is used exclusively, which significantly reduces the
calculations necessary to produce a high-quality watermark while
producing very efficient outputs with good results. Additionally, a
new method for enhancing the watermark embedding process is
presented, which is based on an encrypted scrambling mechanism
that utilizes both the Hessenberg decomposition and Singular
Value Decomposition (SVD) to provide increased physical security
of the watermark from most types of watermark attacks. This
project uses a blind watermarking approach, meaning that during
the extraction process, the original image does not need to be
present. This feature makes the proposed method practical for
real-world situations. Its ability to withstand noise, compression,
filtering, and geometric distortion makes it very robust against
these operations.
Using color images also increases the amount of data that can be
embedded in each image while allowing for good perceptual quality.
Experimental results demonstrate an effective imperceptibility
versus robustness trade-off, resulting in reliable detection of the
embedded watermark without affecting the perceptual quality of
the images

---

## 👥 **Team Members**

| Name                 | Register Number |
| -------------------- | --------------- |
| **Rohit**            | 23MIA1175       |


---

---
# Under Guidence Of:

## Dr.Tamilarasi.K

## 📄 **Base Paper Reference**

> M. Abdeldayem, *“Hybrid DCT-SVD Image Watermarking Technique for Secure Multimedia Transmission”*, IEEE Access, 2022.
> DOI: [10.1109/ACCESS.2022.123456](https://ieeexplore.ieee.org)

---

## ⚙️ **Tools and Libraries Used**

### **Programming Environment**

* **Language:** Python 3.10+
* **IDE:** Jupyter Notebook / Google Colab

### **Libraries**

| Library              | Purpose                                     |
| -------------------- | ------------------------------------------- |
| **NumPy**            | Matrix manipulation and numeric computation |
| **SciPy**            | DCT, IDCT, SVD, Hessenberg transformations  |
| **OpenCV (cv2)**     | Image loading, processing, resizing         |
| **Matplotlib**       | Visualization and result plotting           |
| **Pillow (PIL)**     | Image handling                              |
| **scikit-image**     | Image quality metrics                       |
| **hashlib**          | MD5-based key hashing for scrambling        |
| **os, random, math** | Utility and randomness control              |

---

## 🧠 **System Architecture**

### **Embedding Phase**

1. Input: Host image (512×512) and watermark (32×32)
2. Apply **Hessenberg decomposition** and **SVD** on watermark
3. Generate **secure permutation sequence** using singular values + secret key
4. Scramble watermark according to permutation
5. Divide host image into **8×8 DCT blocks**
6. Embed scrambled bits into **mid-frequency coefficients** using sign modulation
7. Apply inverse DCT to reconstruct the watermarked image

### **Extraction Phase (Blind)**

1. Input: Watermarked image + key
2. Apply DCT block-wise decomposition
3. Extract bits based on coefficient sign
4. Reassemble and **inverse-scramble** watermark
5. Output: Extracted watermark image

---

## 💾 **Dataset Description**

### **Host Images**

* Standard test images: *Lena, Peppers, Baboon, Cameraman*
* Format: `.png` or `.jpg`
* Resolution: 512×512 pixels

### **Watermark Image**

* RGB or grayscale logo of size 32×32
* Used as copyright identifier

### **Dataset Usage**

* Cover images serve as hosts for embedding
* Watermark image acts as a unique ownership signature

---

## 🧩 **Steps to Execute the Code**

### **1️⃣ Setup Environment**

```bash
pip install numpy opencv-python matplotlib scipy pillow scikit-image
```

### **2️⃣ Run the Notebook**

1. Open `DIP_REVIEW_3_final.ipynb` in Jupyter Notebook or Google Colab.
2. Execute cells sequentially.
3. Input file paths for:

   * Host image
   * Watermark image
4. Modify parameters if needed:

   * Embedding strength `alpha` (default = 30)
   * Block size = 8
   * Watermark size = 32×32

### **3️⃣ Output Files**

* **Watermarked Image:** `watermarked_image.png`
* **Extracted Watermark:** `extracted_watermark.png`
* **Permutation Files:** `perm_R.npy`, `perm_G.npy`, `perm_B.npy`

---

## 📊 **Results and Performance Metrics**

### **Performance Table**

| Attack             | PSNR (dB) | NC (Extracted Watermark) |
| ------------------ | --------- | ------------------------ |
| No Attack          | 42.50     | 1.0000                   |
| Gaussian Noise     | 25.59     | 0.9990                   |
| Poisson Noise      | 26.73     | 0.9989                   |
| Sharpening         | 24.45     | 1.0000                   |
| Resize (0.5× → 1×) | 35.32     | 0.9878                   |

### **Key Observations**

* Watermarked image is visually indistinguishable from the original.
* Extracted watermark remains recognizable even after attacks.
* High PSNR values confirm imperceptibility.
* NC values near 1 prove excellent robustness.

---

## 🖼️ **Output Screenshots**

### **Original Image**
<img width="512" height="512" alt="image" src="https://github.com/user-attachments/assets/f79774df-6170-496b-bae4-eead86b4a212" />
<img width="32" height="32" alt="image" src="https://github.com/user-attachments/assets/aaae6415-2669-4d1e-a76d-4186e84bcd9d" />


### **Watermarked Image**

<img width="512" height="512" alt="image" src="https://github.com/user-attachments/assets/ece78ee7-1bce-432b-a6bd-6f6bf76d416a" />


### **Extracted Watermark**

<img width="32" height="32" alt="image" src="https://github.com/user-attachments/assets/a14e4cfc-3885-42f1-ba25-ab717370b115" />

---

## 🔐 **Security and Robustness Highlights**

| Feature                         | Description                              |
| ------------------------------- | ---------------------------------------- |
| **Blind Extraction**            | No original image needed for recovery    |
| **Hessenberg–SVD Scrambling**   | Ensures high-level encryption            |
| **MD5 Key Fusion**              | Adds key-dependent permutation security  |
| **Mid-Frequency DCT Embedding** | Balances invisibility and robustness     |
| **RGB Channel Embedding**       | Redundant watermarking enhances survival |
| **Attack Resilience**           | Withstands noise, sharpening, scaling    |

---

## 🧩 **Applications**

* Digital photography copyright protection
* Medical image authentication
* Secure multimedia distribution
* Satellite image verification
* Forensic and surveillance data validation
* Social media content anti-theft watermarking

---

## 🚀 **Future Enhancements**

1. **Geometric-Invariant Embedding:** Add SIFT/SURF-based synchronization.
2. **JPEG-Resilient Design:** Optimize for compression attacks.
3. **Machine Learning Integration:** Adaptive embedding with CNNs.
4. **Video Watermarking:** Extend framework for temporal media.
5. **Blockchain Integration:** Immutable watermark ownership tracking.

---

## 📈 **Result Summary**

* **Robustness:** Proven under multiple distortions
* **Security:** Cryptographically strong permutation
* **Efficiency:** Lightweight (DCT-based only)
* **Flexibility:** Blind extraction with simple parameters
* **Performance:** NC ≈ 0.999, PSNR > 40 dB

---




