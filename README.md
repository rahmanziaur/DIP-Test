# Image-Processing-Tutorials
In This Repository, we add all the complete tutorial series on Image Processing and Computer Vision with complete Code and Theory. Video lectures are also available - https://www.youtube.com/channel/UCpWIxCtUo2IHh9d3fiyMaJw/playlists

https://colab.research.google.com/drive/1Se2OFSL8HtthdY5hoShGgNb17QtkPZxU


Digital Image and Speech Processing
Lab Viva Question Bank
Part A: Digital Image Processing  |  Part B: Speech Processing & Algorithms


Below is a **GitHub-ready `README.md`** with **questions and answers included**, well-structured with **Table of Contents, headings, and formatting** so it renders cleanly on GitHub.

You can **copy and paste directly into `README.md`**.

---

# Image-Processing-Tutorials

Complete tutorials on **Digital Image Processing, Computer Vision, and Speech Processing** with **theory, algorithms, and code implementations**.

This repository provides **concept explanations, lab materials, and viva questions with answers** for undergraduate students studying **Image Processing and Speech Processing**.

---

## Learning Resources

### YouTube Video Lectures

Full tutorial playlist:

[https://www.youtube.com/channel/UCpWIxCtUo2IHh9d3fiyMaJw/playlists](https://www.youtube.com/channel/UCpWIxCtUo2IHh9d3fiyMaJw/playlists)

### Google Colab Notebook

Run the examples online:

[https://colab.research.google.com/drive/1Se2OFSL8HtthdY5hoShGgNb17QtkPZxU](https://colab.research.google.com/drive/1Se2OFSL8HtthdY5hoShGgNb17QtkPZxU)

---

# Digital Image and Speech Processing

## Lab Viva Question Bank

**Total Questions:** 70
**Difficulty Level:** Easy – Medium
**Level:** Undergraduate

Covered topics include **Digital Image Processing, Speech Processing, and Graph Algorithms**.

---

# Table of Contents

* Part A: Digital Image Processing

  * Fundamentals
  * Color Models
  * Image Enhancement
  * Image Transforms
  * Segmentation & Features
  * Image Compression

* Part B: Speech Processing

  * Phonetics
  * Signal Analysis
  * Feature Extraction
  * Speech Recognition
  * Graph Algorithms

---

# Part A: Digital Image Processing

## Fundamentals

### Q1. What is Digital Image Processing?

**Answer**

Digital Image Processing is the manipulation and analysis of images using digital computers. Images are represented as **2D matrices of pixels**, and algorithms are applied to perform operations such as:

* Image enhancement
* Noise reduction
* Compression
* Segmentation
* Feature extraction

---

### Q2. What is a pixel and how is an image represented digitally?

**Answer**

A **pixel (picture element)** is the smallest unit of a digital image.

An image is represented as a **2D matrix**

```
f(x, y)
```

Where

* **x, y** → spatial coordinates
* **f(x,y)** → intensity value

For an **M × N image**, the matrix contains **M rows and N columns**.

---

### Q3. What is image sampling and quantization?

**Answer**

**Sampling**

Converting a continuous image into a grid of pixels.

**Quantization**

Mapping continuous intensity values into a finite number of levels.

Example:

8-bit image → **256 gray levels**

---

### Q4. What are the basic relationships between pixels?

**Answer**

Important pixel relationships include:

1. **Neighbors**

   * 4-neighbors (N, S, E, W)
   * Diagonal neighbors
   * 8-neighbors

2. **Adjacency**

Pixels are adjacent if they are neighbors and satisfy a condition.

3. **Connectivity**

A path exists between pixels through adjacent pixels.

4. **Distance Measures**

* Euclidean distance
* City-block distance
* Chessboard distance

---

### Q5. Difference between 4-connectivity and 8-connectivity?

**Answer**

**4-connectivity**

Pixel connected only to:

* Up
* Down
* Left
* Right

**8-connectivity**

Pixel connected to **all eight surrounding pixels including diagonals**.

8-connectivity is widely used in **image segmentation**.

---

### Q6. What is spatial resolution and gray-level resolution?

**Answer**

**Spatial Resolution**

Number of pixels used to represent an image.

Example:

```
512 × 512
```

Higher resolution → more image detail.

**Gray-Level Resolution**

Number of intensity levels.

Example:

8-bit image → **256 levels**

---

### Q7. What is aliasing in image sampling?

**Answer**

Aliasing occurs when the **sampling rate is too low** to capture image details.

High-frequency components appear as incorrect patterns.

To prevent aliasing:

* Use **Nyquist sampling theorem**
* Apply **low-pass anti-aliasing filter**

---

# Color Models

### Q8. What is the RGB color model?

**Answer**

RGB is an **additive color model** using:

* Red
* Green
* Blue

Each component ranges from **0 – 255**.

Examples:

White

```
(255,255,255)
```

Black

```
(0,0,0)
```

Used in **monitors and cameras**.

---

### Q9. What is the HSV color model?

**Answer**

HSV stands for:

H → Hue (color type)
S → Saturation (color intensity)
V → Value (brightness)

HSV is more intuitive for **human color perception**.

---

### Q10. What is the CMY color model?

**Answer**

CMY stands for:

* Cyan
* Magenta
* Yellow

Used in **printing systems**.

Conversion from RGB:

```
C = 1 − R
M = 1 − G
Y = 1 − B
```

CMYK adds **Black (K)**.

---

# Image Enhancement

### Q13. What is gray level transformation?

**Answer**

A gray level transformation modifies pixel intensities.

Mathematical form:

```
s = T(r)
```

Where

* r → input intensity
* s → output intensity

Examples:

* Image negative
* Log transform
* Gamma correction
* Thresholding

---

### Q14. What is histogram equalization?

**Answer**

Histogram equalization improves image contrast by **redistributing pixel intensities**.

Formula:

```
s_k = (L − 1) Σ (n_j / N)
```

Where

* L → number of intensity levels
* n_j → number of pixels with intensity j
* N → total pixels

---

### Q16. What are spatial smoothing filters?

**Answer**

Used to **reduce noise and blur images**.

Common filters:

**Mean Filter**

Average of neighborhood pixels.

**Median Filter**

Median value of neighbors.

Good for **salt-and-pepper noise**.

**Gaussian Filter**

Weighted average using Gaussian distribution.

---

# Image Transforms

### Q19. What is Discrete Fourier Transform (DFT)?

**Answer**

DFT converts an image from **spatial domain to frequency domain**.

Low frequencies → smooth regions
High frequencies → edges and noise

FFT computes DFT efficiently in:

```
O(N log N)
```

---

### Q20. What is Discrete Cosine Transform (DCT)?

**Answer**

DCT represents data using **cosine functions**.

It is widely used in **JPEG image compression** because it concentrates energy in a few coefficients.

---

# Segmentation

### Q24. What is image segmentation?

**Answer**

Image segmentation divides an image into **meaningful regions**.

Methods include:

* Thresholding
* Edge detection
* Region growing
* Clustering (K-means)

---

### Q25. What is edge detection?

**Answer**

Edge detection identifies **sharp intensity changes**.

Common operators:

* Sobel
* Prewitt
* Canny

Canny is considered the **most accurate edge detector**.

---

# Image Compression

### Q29. What is image compression?

**Answer**

Image compression reduces the number of bits required to store an image.

Reasons:

* Reduce storage
* Faster transmission

---

### Q30. Difference between lossless and lossy compression?

**Answer**

**Lossless Compression**

Original image can be perfectly reconstructed.

Examples:

* PNG
* Huffman Coding
* LZW

**Lossy Compression**

Some data is discarded.

Example:

* JPEG

Provides **higher compression ratios**.

---

# Part B: Speech Processing

## Phonetics

### Q36. What is articulatory phonetics?

**Answer**

Articulatory phonetics studies **how speech sounds are produced by the human vocal tract**.

It analyzes movement of:

* Tongue
* Lips
* Teeth
* Vocal cords

---

### Q39. What is the difference between voiced and voiceless sounds?

**Answer**

**Voiced sounds**

Produced with **vocal cord vibration**.

Examples:

b, d, g, vowels

**Voiceless sounds**

Produced **without vibration**.

Examples:

p, t, s

---

# Signal Analysis

### Q43. What is Short-Time Fourier Transform (STFT)?

**Answer**

STFT divides a speech signal into **short frames (20–30 ms)** and computes the Fourier Transform of each frame.

Used because speech signals are **non-stationary**.

Output → **spectrogram**.

---

### Q44. What is a spectrogram?

**Answer**

A spectrogram shows how frequency changes over time.

Axes:

* X → Time
* Y → Frequency
* Color → Magnitude

---

# Feature Extraction

### Q48. What are MFCCs?

**Answer**

MFCC stands for **Mel Frequency Cepstral Coefficients**.

They are the most widely used features in speech recognition.

Steps:

1. Pre-emphasis
2. Framing
3. FFT
4. Mel filterbank
5. Log energy
6. DCT

---

# Speech Recognition

### Q56. Main components of a speech recognition system?

**Answer**

1. Feature extraction
2. Acoustic model
3. Pronunciation lexicon
4. Language model
5. Decoder

---

# Graph Algorithms

### Q67. What is Dijkstra's algorithm?

**Answer**

Dijkstra's algorithm finds the **shortest path from a source node to all other nodes** in a graph with **non-negative weights**.

Steps:

1. Initialize distances
2. Use priority queue
3. Relax edges
4. Update shortest distances

Time complexity:

```
O((V + E) log V)
```

---

