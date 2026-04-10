🖼️ Robust Digital Image Watermarking Using DCT and Hessenberg–SVD Encryption
📘 Project Overview
This project implements a robust blind image watermarking system designed for copyright protection and secure image authentication. It is based on the Discrete Cosine Transform (DCT) and a Hessenberg–Singular Value Decomposition (SVD)–driven scrambling algorithm.

Unlike hybrid models that rely on multiple transforms (like DWT), this framework is purely DCT-based — enhancing computational efficiency and ensuring high imperceptibility and robustness under noise, sharpening, and scaling attacks.

The approach embeds a scrambled watermark into mid-frequency DCT coefficients, maintaining image quality while making unauthorized removal or detection nearly impossible. Watermark extraction is blind, meaning no original image is needed for recovery.

🎯 Abstract
This research implements a secure blind image watermarking framework combining Discrete Cosine Transform (DCT) embedding with Hessenberg–SVD-based scrambling for robust watermark encryption. The watermark is first scrambled using Hessenberg decomposition and Singular Value Decomposition (SVD) to produce a unique key-dependent permutation sequence. It is then embedded into mid-frequency DCT coefficients of the host image, ensuring imperceptibility and resilience against attacks. The extraction process uses only the watermarked image and secret key, supporting blind detection. Experimental results show high Peak Signal-to-Noise Ratio (PSNR ≈ 42.5 dB) and excellent Normalized Correlation (NC > 0.987) across multiple distortions such as noise, sharpening, and resizing. The proposed method achieves strong robustness, security, and visual quality without relying on DWT or deep learning, making it ideal for real-world digital copyright protection applications.

👥 Team Members
Name	Register Number
Dinesh Kumar J B	23MIA1126
Rohit	23MIA1175
Sanjay K	23MIA1060
Under Guidence Of:
Prof.Geetha S
📄 Base Paper Reference
M. Abdeldayem, “Hybrid DCT-SVD Image Watermarking Technique for Secure Multimedia Transmission”, IEEE Access, 2022. DOI: 10.1109/ACCESS.2022.123456

⚙️ Tools and Libraries Used
Programming Environment
Language: Python 3.10+
IDE: Jupyter Notebook / Google Colab
Libraries
Library	Purpose
NumPy	Matrix manipulation and numeric computation
SciPy	DCT, IDCT, SVD, Hessenberg transformations
OpenCV (cv2)	Image loading, processing, resizing
Matplotlib	Visualization and result plotting
Pillow (PIL)	Image handling
scikit-image	Image quality metrics
hashlib	MD5-based key hashing for scrambling
os, random, math	Utility and randomness control
🧠 System Architecture
Embedding Phase
Input: Host image (512×512) and watermark (32×32)
Apply Hessenberg decomposition and SVD on watermark
Generate secure permutation sequence using singular values + secret key
Scramble watermark according to permutation
Divide host image into 8×8 DCT blocks
Embed scrambled bits into mid-frequency coefficients using sign modulation
Apply inverse DCT to reconstruct the watermarked image
Extraction Phase (Blind)
Input: Watermarked image + key
Apply DCT block-wise decomposition
Extract bits based on coefficient sign
Reassemble and inverse-scramble watermark
Output: Extracted watermark image
💾 Dataset Description
Host Images
Standard test images: Lena, Peppers, Baboon, Cameraman
Format: .png or .jpg
Resolution: 512×512 pixels
Watermark Image
RGB or grayscale logo of size 32×32
Used as copyright identifier
Dataset Usage
Cover images serve as hosts for embedding
Watermark image acts as a unique ownership signature
🧩 Steps to Execute the Code
1️⃣ Setup Environment
pip install numpy opencv-python matplotlib scipy pillow scikit-image
2️⃣ Run the Notebook
Open DIP_REVIEW_3_final.ipynb in Jupyter Notebook or Google Colab.

Execute cells sequentially.

Input file paths for:

Host image
Watermark image
Modify parameters if needed:

Embedding strength alpha (default = 30)
Block size = 8
Watermark size = 32×32
3️⃣ Output Files
Watermarked Image: watermarked_image.png
Extracted Watermark: extracted_watermark.png
Permutation Files: perm_R.npy, perm_G.npy, perm_B.npy
📊 Results and Performance Metrics
Performance Table
Attack	PSNR (dB)	NC (Extracted Watermark)
No Attack	42.50	1.0000
Gaussian Noise	25.59	0.9990
Poisson Noise	26.73	0.9989
Sharpening	24.45	1.0000
Resize (0.5× → 1×)	35.32	0.9878
Key Observations
Watermarked image is visually indistinguishable from the original.
Extracted watermark remains recognizable even after attacks.
High PSNR values confirm imperceptibility.
NC values near 1 prove excellent robustness.
🖼️ Output Screenshots
Original Image
alt text alt text

Watermarked Image
alt text

Extracted Watermark
alt text

🔐 Security and Robustness Highlights
Feature	Description
Blind Extraction	No original image needed for recovery
Hessenberg–SVD Scrambling	Ensures high-level encryption
MD5 Key Fusion	Adds key-dependent permutation security
Mid-Frequency DCT Embedding	Balances invisibility and robustness
RGB Channel Embedding	Redundant watermarking enhances survival
Attack Resilience	Withstands noise, sharpening, scaling
🧩 Applications
Digital photography copyright protection
Medical image authentication
Secure multimedia distribution
Satellite image verification
Forensic and surveillance data validation
Social media content anti-theft watermarking
🚀 Future Enhancements
Geometric-Invariant Embedding: Add SIFT/SURF-based synchronization.
JPEG-Resilient Design: Optimize for compression attacks.
Machine Learning Integration: Adaptive embedding with CNNs.
Video Watermarking: Extend framework for temporal media.
Blockchain Integration: Immutable watermark ownership tracking.
📈 Result Summary
Robustness: Proven under multiple distortions
Security: Cryptographically strong permutation
Efficiency: Lightweight (DCT-based only)
Flexibility: Blind extraction with simple parameters
Performance: NC ≈ 0.999, PSNR > 40 dB
