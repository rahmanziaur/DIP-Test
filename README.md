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

Below is a **clean GitHub `README.md` style section** where the **questions and answers are properly formatted** using Markdown headings, numbering, and difficulty tags. You can paste this directly into your repository.

---

# Digital Image Processing — Viva Questions with Answers

## Fundamentals

### Q1. What is digital image processing? *(Easy)*

**Answer:**
Digital image processing refers to the manipulation of images using digital computers. It involves applying algorithms to acquire, enhance, compress, restore, and analyze images in digital form. A digital image is typically represented as a **2D array (matrix) of pixels**, where each pixel contains intensity or color information.

---

### Q2. What is a pixel and how is an image represented digitally? *(Easy)*

**Answer:**
A **pixel (picture element)** is the smallest unit of a digital image.

A digital image is represented as a **2D matrix**:

```
f(x, y)
```

Where:

* **x, y** → spatial coordinates
* **f(x, y)** → intensity value (gray level or color)

For an **M × N image**, the matrix contains:

* **M rows**
* **N columns**

Each element represents one pixel value.

---

### Q3. What is image sampling and quantization? *(Easy)*

**Answer:**

Digital image creation involves two main processes:

**1. Sampling**
Sampling converts a continuous image into a **discrete grid of pixels**.
It determines the **spatial resolution** of the image.

Example:

Continuous Image → Sampled Grid → Pixels

**2. Quantization**
Quantization converts continuous intensity values into **finite discrete levels**.

Example:

* **8-bit image → 256 gray levels**
* **10-bit image → 1024 gray levels**

Together, **sampling + quantization** determine the **digital resolution of the image**.

---

### Q4. What are the basic relationships between pixels? *(Easy)*

**Answer:**

Important pixel relationships include:

**1. Neighbors**

* **4-neighbors:** North, South, East, West
* **Diagonal neighbors**
* **8-neighbors:** All surrounding pixels

**2. Adjacency**

Two pixels are adjacent if they are neighbors **and satisfy a gray-level condition**.

**3. Connectivity**

Two pixels are connected if a **path exists through adjacent pixels**.

**4. Distance Measures**

Common pixel distance metrics:

* **Euclidean distance**
* **City-block distance (D4)**
* **Chessboard distance (D8)**

These relationships are important in **segmentation, region analysis, and morphology**.

---

### Q5. What is the difference between 4-connectivity and 8-connectivity? *(Easy)*

**Answer:**

**4-connectivity**

A pixel is connected only to its **horizontal and vertical neighbors**:

```
   N
W  P  E
   S
```

Neighbors: **North, South, East, West**

---

**8-connectivity**

A pixel is connected to **all surrounding pixels**, including diagonals:

```
NW   N   NE
W    P    E
SW   S   SE
```

Neighbors: **8 total**

---

**Comparison**

| Connectivity   | Neighbors | Usage                             |
| -------------- | --------- | --------------------------------- |
| 4-connectivity | 4         | Simpler connectivity              |
| 8-connectivity | 8         | More complete region connectivity |

8-connectivity is commonly used in **image segmentation and labeling**.

---

### Q6. What is spatial resolution and gray-level resolution? *(Medium)*

**Answer:**

**Spatial Resolution**

Spatial resolution refers to the **smallest detail that can be distinguished in an image**.
It depends on the **number of pixels**.

Example:

* 256 × 256 → low spatial resolution
* 1024 × 1024 → higher spatial resolution

Higher pixel count → **more image detail**

---

**Gray-Level Resolution**

Gray-level resolution refers to the **number of intensity levels available for each pixel**.

Example:

| Bit Depth | Gray Levels |
| --------- | ----------- |
| 1-bit     | 2           |
| 8-bit     | 256         |
| 16-bit    | 65,536      |

Higher gray-level resolution → **smoother intensity transitions**.

---

### Q7. What is aliasing in image sampling? *(Medium)*

**Answer:**

**Aliasing** occurs when the **sampling rate is too low** to capture the highest spatial frequencies of an image.

As a result:

* High-frequency details appear as **false patterns**
* Fine textures become **distorted**

This phenomenon is explained by the **Nyquist Sampling Theorem**:

> The sampling rate must be **at least twice the highest frequency** present in the signal.

To prevent aliasing:

* Apply **anti-aliasing filters (low-pass filters)** before sampling.

---

# Color Models

### Q8. What is the RGB color model? *(Easy)*

**Answer:**

The **RGB color model** is an **additive color model** where colors are created by combining:

* **Red**
* **Green**
* **Blue**

Each component typically ranges from:

```
0 – 255
```

Examples:

| Color | RGB           |
| ----- | ------------- |
| Black | (0,0,0)       |
| White | (255,255,255) |
| Red   | (255,0,0)     |
| Green | (0,255,0)     |
| Blue  | (0,0,255)     |

RGB is used in:

* Computer displays
* Cameras
* Mobile screens
* Digital graphics

---

### Q9. What is the HSV color model and its components? *(Easy)*

**Answer:**

HSV stands for:

| Component | Meaning                   |
| --------- | ------------------------- |
| **H**     | Hue (color type)          |
| **S**     | Saturation (color purity) |
| **V**     | Value (brightness)        |

**Hue**

Represents the color angle:

```
0° – 360°
```

Examples:

* 0° → Red
* 120° → Green
* 240° → Blue

---

**Saturation**

Measures color intensity:

```
0 → gray
1 → fully saturated
```

---

**Value**

Represents brightness:

```
0 → black
1 → full brightness
```

HSV is **more intuitive for humans** when selecting colors.

---

### Q10. What is the CMY color model and where is it used? *(Easy)*

**Answer:**

The **CMY color model** is a **subtractive color model** used in **printing systems**.

Components:

* **C** → Cyan
* **M** → Magenta
* **Y** → Yellow

Unlike RGB, colors are created by **subtracting light from white**.

Conversion from RGB:

```
C = 1 − R
M = 1 − G
Y = 1 − B
```

---

**CMYK Model**

Printing often adds **Black (K)**:

```
CMYK = Cyan + Magenta + Yellow + Black
```

Benefits of K channel:

* Improves dark tones
* Reduces ink cost
* Improves print sharpness

---

### Q11. What is the YIQ color model? *(Medium)*

**Answer:**

The **YIQ color model** was used in **NTSC television broadcasting**.

Components:

| Component | Meaning                |
| --------- | ---------------------- |
| **Y**     | Luminance (brightness) |
| **I**     | In-phase chrominance   |
| **Q**     | Quadrature chrominance |

Key idea:

Separate **brightness information** from **color information**.

Advantages:

* Compatible with **black-and-white televisions**
* Efficient **bandwidth usage**

Modern systems often use **YCbCr instead**.

---

### Q12. How do you convert from RGB to HSV? *(Medium)*

**Answer:**

Given normalized values:

```
R, G, B ∈ [0,1]
```

Step 1:

```
MAX = max(R,G,B)
MIN = min(R,G,B)
delta = MAX − MIN
```

Step 2: Value

```
V = MAX
```

Step 3: Saturation

```
S = delta / MAX   (if MAX ≠ 0)
S = 0             (if MAX = 0)
```

Step 4: Hue

```
If MAX = R → H = 60 * ((G − B)/delta mod 6)
If MAX = G → H = 60 * ((B − R)/delta + 2)
If MAX = B → H = 60 * ((R − G)/delta + 4)
```

Final range:

```
H ∈ [0°,360°]
S ∈ [0,1]
V ∈ [0,1]
```

---


Here’s a clean, well-structured **GitHub README.md format** using headings, code blocks, and bullet points:

---

```markdown
# 📘 Image Processing, Compression & Speech Processing – Q&A

---

## 🖼️ Image Enhancement

### Q13. What is a gray level transformation?  [Easy]
**Answer:**
A gray level transformation (also called point operation or intensity transformation) maps each pixel's intensity value to a new value using a function:

```

s = T(r)

```

- `r` = input intensity  
- `s` = output intensity  

**Examples:**
- Image negative  
- Thresholding  
- Log transformation  
- Power-law (gamma) transformation  

---

### Q14. What is histogram equalization?  [Easy]
**Answer:**
Histogram equalization enhances image contrast by redistributing pixel intensities so the histogram becomes approximately uniform.

```

s_k = (L - 1) * Σ (n_j / N),  j = 0 → k

```

- `n_j` = number of pixels with intensity `j`  
- `N` = total number of pixels  

---

### Q15. Spatial vs Frequency Domain Enhancement  [Medium]

| Spatial Domain | Frequency Domain |
|---------------|----------------|
| Operates directly on pixels | Works on transformed image |
| Uses convolution (filters) | Uses transforms (DFT) |
| Examples: smoothing, sharpening | Examples: low-pass, high-pass filtering |
| Simple for small kernels | Efficient for large kernels |

---

### Q16. Spatial Operations for Image Smoothing  [Easy]

**Answer:**
- **Mean Filter:** Average of neighborhood  
- **Median Filter:** Median value (good for salt & pepper noise)  
- **Gaussian Filter:** Weighted average using Gaussian kernel  

---

### Q17. What is image sharpening?  [Medium]

**Answer:**
Enhances edges and fine details by emphasizing high-frequency components.

**Techniques:**
1. Laplacian filter  
2. Unsharp masking  
3. High-boost filtering  

```

f_hb = A * f - f_smooth

```

---

### Q18. What is multispectral image enhancement?  [Medium]

**Answer:**
Enhances images from multiple spectral bands (e.g., satellite images).

- Improves contrast and color representation  
- Applied per-band or across bands  
- Uses PCA for decorrelation  

---

## 🔄 TRANSFORMS

### Q19. What is the Discrete Fourier Transform (DFT)?  [Medium]

**Answer:**
- Converts image from spatial → frequency domain  
- Low frequency = smooth areas  
- High frequency = edges/noise  

**FFT Complexity:**
```

O(N log N)

```

---

### Q20. What is the Discrete Cosine Transform (DCT)?  [Easy]

**Answer:**
- Represents data using cosine functions  
- Used in JPEG compression  
- Applied on 8×8 blocks  
- Uses real numbers only  

---

### Q21. What is the Haar transform?  [Medium]

**Answer:**
- Simplest wavelet transform  
- Uses step functions  
- Decomposes signal into:
  - Averages  
  - Differences  

---

### Q22. Wavelet Transform vs DFT  [Medium]

| Wavelet Transform | DFT |
|------------------|-----|
| Time + Frequency info | Only frequency |
| Multi-resolution | Single resolution |
| Good for edges/local features | Global analysis |

---

### Q23. What is the convolution theorem?  [Medium]

**Answer:**
```

f(x,y) * h(x,y) ↔ F(u,v) · H(u,v)

```

- Convolution in spatial domain = multiplication in frequency domain  
- Enables efficient filtering  

---

## 🧩 SEGMENTATION & FEATURES

### Q24. What is image segmentation?  [Easy]

**Answer:**
Divides an image into meaningful regions.

**Methods:**
- Thresholding  
- Edge detection  
- Region growing  
- Clustering (k-means)  

---

### Q25. What is edge detection?  [Easy]

**Answer:**
Detects intensity changes (object boundaries).

**Operators:**
- Sobel  
- Prewitt  
- Canny (best)  

---

### Q26. Steps of Canny Edge Detector  [Medium]

1. Gaussian smoothing  
2. Gradient computation  
3. Non-maximum suppression  
4. Double thresholding  
5. Edge tracking (hysteresis)  

---

### Q27. What is region growing?  [Medium]

**Answer:**
- Starts from seed pixels  
- Adds similar neighboring pixels  
- Stops when no more pixels satisfy condition  

---

### Q28. Spatial features in image analysis  [Medium]

**Examples:**
- Area  
- Perimeter  
- Compactness  
- Moments (centroid, orientation)  
- Texture (GLCM)  

---

## 📦 COMPRESSION

### Q29. What is image compression?  [Easy]

**Answer:**
Reduces bits required to represent an image.

**Removes:**
- Spatial redundancy  
- Spectral redundancy  
- Psychovisual redundancy  

---

### Q30. Lossless vs Lossy Compression  [Easy]

| Lossless | Lossy |
|----------|-------|
| No data loss | Some data loss |
| Exact reconstruction | Approximate |
| PNG, Huffman, LZW | JPEG |
| Lower compression | Higher compression |

---

### Q31. How JPEG compression works  [Medium]

1. RGB → YCbCr  
2. 8×8 blocks  
3. Apply DCT  
4. Quantization (lossy step)  
5. Zigzag scan  
6. Huffman coding  

---

### Q32. What is predictive coding?  [Medium]

**Answer:**
Encodes difference between actual and predicted pixel.

- Uses neighboring pixels  
- Example: **DPCM**  

---

### Q33. What is MPEG?  [Medium]

**Answer:**
Video compression standard using temporal redundancy.

**Frame types:**
- I-frame (independent)  
- P-frame (predicted)  
- B-frame (bi-directional)  

---

### Q34. What is Huffman coding?  [Easy]

**Answer:**
- Assigns shorter codes to frequent symbols  
- Builds binary tree  
- Produces optimal prefix-free codes  

---

### Q35. What is transform coding?  [Medium]

**Answer:**
- Converts image to transform domain (DCT/DWT)  
- Energy concentrated in few coefficients  
- Enables efficient compression  

---

# 🎤 Part B: Speech Processing

---

## 🔊 PHONETICS

### Q36. What is articulatory phonetics?  [Easy]

**Answer:**
Studies how speech sounds are produced using:
- Tongue  
- Lips  
- Teeth  
- Velum  
- Glottis  

---

### Q37. Components of vocal tract  [Easy]

- Lungs (air source)  
- Larynx (vocal folds)  
- Pharynx  
- Oral cavity  
- Nasal cavity  

---

### Q38. Classification of speech sounds  [Easy]

- **Vowels** (open tract)  
- **Consonants** (obstruction)  
- **Semi-vowels** (/w/, /j/)  

---

### Q39. Voiced vs Voiceless sounds  [Easy]

| Voiced | Voiceless |
|--------|----------|
| Vocal folds vibrate | No vibration |
| Example: /b/, /z/ | Example: /p/, /s/ |

---

### Q40. What is acoustic phonetics?  [Easy]

**Answer:**
Studies sound wave properties:
- Frequency (F0)  
- Formants  
- Intensity  
- Duration  

---

### Q41. What are formants?  [Medium]

**Answer:**
Resonant frequencies of vocal tract.

- F1 → vowel height  
- F2 → tongue position  

---

### Q42. Source-filter model  [Medium]

```

s(t) = source(t) * filter(t)

```

- Source: glottal pulse / noise  
- Filter: vocal tract  

---

## 📊 SIGNAL ANALYSIS

### Q43. What is STFT?  [Easy]

**Answer:**
- Splits signal into short frames (20–30 ms)  
- Applies Fourier Transform  

**Output:** Spectrogram (time-frequency representation)
```

---

# Signal Analysis

### Q43. What is Short-Time Fourier Transform (STFT)?

**Answer**

STFT divides a speech signal into **short frames (20–30 ms)** and computes the Fourier Transform of each frame.

Used because speech signals are **non-stationary**.

Output → **spectrogram**.

---

Below is the **GitHub `README.md` formatted continuation** for **Q44 – Q70**, using the **same style as the previous section** (clear headings, answers, and code blocks for formulas).

You can **append this directly to your README.md file**.

---

# Signal Analysis

## Q44. What is a spectrogram? [Easy]

**Answer**

A **spectrogram** is a **2D visualization of a speech signal** showing how the frequency content changes over time.

Axes:

* **X-axis:** Time
* **Y-axis:** Frequency
* **Color/Intensity:** Magnitude of frequency components

Spectrograms are computed using the **Short-Time Fourier Transform (STFT)**.

Types of spectrograms:

**Narrowband Spectrogram**

* High frequency resolution
* Shows **formant structure**

**Wideband Spectrogram**

* High time resolution
* Shows **glottal pulses**

---

## Q45. What is the role of windowing in STFT? [Medium]

**Answer**

Windowing is applied before computing the **Fourier Transform** for each speech frame.

Each frame is multiplied by a **window function** such as:

* Hamming window
* Hanning window

Purpose:

* Reduces **spectral leakage**
* Improves frequency analysis accuracy

Common window used in speech processing:

```
w(n) = 0.54 − 0.46 cos(2πn/(N−1))
```

This is the **Hamming window**.

---

## Q46. What are filters in speech processing? [Medium]

**Answer**

Filters modify the **frequency content of speech signals**.

Three important types:

### Pre-emphasis Filter

High-pass filter used before analysis.

```
H(z) = 1 − 0.97z⁻¹
```

Purpose:

* Boost high frequencies
* Compensate spectral tilt

### Analysis Filters

Filterbanks that divide speech into frequency bands.

Examples:

* Mel filterbank
* Bark filterbank

### Synthesis Filters

Used to **reconstruct speech signals**.

Commonly used in:

* LPC synthesis
* Vocoders

---

# Speech Features

## Q47. What are features in speech processing? [Easy]

**Answer**

Features are **compact numerical representations of speech signals** used for machine learning and recognition tasks.

Good features should be:

* **Discriminative**
* **Robust to noise**
* **Compact**

Common speech features include:

* MFCC (Mel Frequency Cepstral Coefficients)
* LPC coefficients
* PLP coefficients
* Energy
* Zero-crossing rate

---

## Q48. What are MFCCs and how are they computed? [Easy]

**Answer**

**MFCC (Mel Frequency Cepstral Coefficients)** are the most widely used features in speech recognition.

Computation steps:

1. Pre-emphasis
2. Framing and windowing
3. Fast Fourier Transform (FFT)
4. Apply Mel-scale filterbank
5. Take logarithm of filter energies
6. Apply Discrete Cosine Transform (DCT)

Typical feature vector:

* **12–13 MFCC coefficients**
* Plus **delta and delta-delta features**

---

## Q49. What is the mel scale and why is it used? [Easy]

**Answer**

The **Mel scale** is a perceptual frequency scale that approximates **human hearing perception**.

Properties:

* Linear below **1 kHz**
* Logarithmic above **1 kHz**

Conversion formula:

```
mel = 2595 log10(1 + f/700)
```

Mel-scale filterbanks simulate the **human auditory system**, making speech features more robust.

---

## Q50. What are LPC coefficients? [Medium]

**Answer**

**Linear Predictive Coding (LPC)** models the speech signal using a **linear prediction model**.

The current speech sample is predicted from previous samples:

```
s(n) = Σ a_k s(n-k)
```

Where:

* **aₖ** → LPC coefficients

LPC represents the **spectral envelope of speech** and captures **vocal tract characteristics**.

Estimated using:

* Autocorrelation method
* Levinson–Durbin algorithm

---

## Q51. What are PLP coefficients? [Medium]

**Answer**

**Perceptual Linear Prediction (PLP)** combines **auditory perception models** with LPC analysis.

Steps:

1. Compute power spectrum
2. Apply Bark-scale filterbank
3. Apply equal-loudness weighting
4. Apply cubic root compression
5. Fit autoregressive model

Advantages:

* Models human auditory perception
* More robust to **speaker variability**

---

## Q52. What is log spectral distance (LSD)? [Medium]

**Answer**

Log Spectral Distance measures the **difference between two spectral envelopes**.

Formula:

```
LSD = sqrt[(1/(2π)) ∫ (log P1(ω) − log P2(ω))² dω]
```

Properties:

* Perceptually meaningful
* Used in **speech coding evaluation**
* Measures spectral distortion

---

## Q53. What are cepstral distances and why are they preferred? [Medium]

**Answer**

Cepstral distance measures distortion between **two cepstral vectors**.

Formula:

```
CD = sqrt[ Σ (c1(n) − c2(n))² ]
```

Advantages:

* Cepstral coefficients are nearly **uncorrelated**
* Efficient computation
* Closely related to **perceptual speech quality**

---

## Q54. What is Dynamic Time Warping (DTW)? [Medium]

**Answer**

Dynamic Time Warping aligns two time sequences by **warping the time axis**.

Purpose:

Handle differences in **speaking speed**.

Steps:

1. Construct distance matrix
2. Compute optimal alignment path
3. Minimize cumulative distance

DTW uses **dynamic programming**.

Applications:

* Speech recognition
* Signature verification
* Gesture recognition

---

# Speech Recognition

## Q55. What is a Large Vocabulary Continuous Speech Recognition (LVCSR) system? [Easy]

**Answer**

LVCSR converts **continuous speech into text** using a large vocabulary.

Challenges:

* Co-articulation
* Speaker variability
* Language complexity

Modern systems use:

* Deep Neural Networks
* Transformer models
* Beam search decoding

---

## Q56. What are the main components of a speech recognition system? [Easy]

**Answer**

1. **Feature Extraction**

Extract acoustic features such as MFCCs.

2. **Acoustic Model**

Maps features to phonemes.

Examples:

* HMM-GMM
* Deep Neural Networks

3. **Pronunciation Lexicon**

Maps words to phoneme sequences.

4. **Language Model**

Assigns probabilities to word sequences.

5. **Decoder**

Finds the most probable word sequence.

---

## Q57. What is a Hidden Markov Model (HMM)? [Medium]

**Answer**

HMM models speech as a sequence of **hidden states**.

Components:

* States → phoneme segments
* Transitions → temporal changes
* Emissions → observed acoustic features

Recognition uses the **Viterbi algorithm** to find the most likely state sequence.

---

## Q58. What is speaker recognition and how does it differ from speech recognition? [Easy]

**Answer**

**Speech Recognition**

Identifies **what is being said**.

**Speaker Recognition**

Identifies **who is speaking**.

Types:

1. **Speaker Verification**

1:1 identity confirmation.

2. **Speaker Identification**

1:N speaker matching.

Features used:

* MFCC
* i-vectors
* x-vectors

---

## Q59. What is pitch estimation in speech? [Medium]

**Answer**

Pitch represents the **fundamental frequency (F0)** of speech.

Typical ranges:

* Male: 80–150 Hz
* Female: 150–300 Hz

Methods:

1. Autocorrelation
2. AMDF
3. Cepstrum analysis

Applications:

* Prosody analysis
* Speaker recognition
* Voice conversion

---

## Q60. What is speech restoration? [Medium]

**Answer**

Speech restoration aims to **recover clean speech from noisy signals**.

Techniques include:

1. Spectral subtraction
2. Wiener filtering
3. Deep learning models

Applications:

* Hearing aids
* Telecommunication
* Speech recognition systems

---

## Q61. What is speaker separation (Cocktail Party Problem)? [Medium]

**Answer**

Speaker separation isolates **individual voices from mixed speech signals**.

Methods include:

1. Beamforming
2. Independent Component Analysis (ICA)
3. Deep learning models

Examples of modern models:

* Deep clustering
* PIT (Permutation Invariant Training)
* Conv-TasNet

---

# Graph Algorithms

## Q62. What is a greedy algorithm? [Easy]

**Answer**

A greedy algorithm makes the **best local decision at each step**.

Example:

* Dijkstra's shortest path
* Activity selection problem

Advantages:

* Fast
* Simple implementation

However, it does **not always guarantee global optimality**.

---

## Q63. What is the multistage graph problem? [Medium]

**Answer**

A **multistage graph** is a directed graph divided into stages.

Edges only connect:

```
stage i → stage i+1
```

Goal:

Find the **minimum-cost path from source to sink**.

Solved using **dynamic programming**.

```
cost(v) = min [ c(v,u) + cost(u) ]
```

---

## Q64. What is the All Pairs Shortest Path (APSP) problem? [Medium]

**Answer**

APSP computes shortest paths between **all pairs of vertices**.

Classic algorithm:

**Floyd–Warshall**

Update rule:

```
d[i][j] = min(d[i][j], d[i][k] + d[k][j])
```

Time complexity:

```
O(V³)
```

---

## Q65. What is the Floyd–Warshall algorithm? [Medium]

**Answer**

Floyd–Warshall computes **all-pairs shortest paths** using dynamic programming.

Algorithm:

For each intermediate vertex **k**

```
D[i][j] = min(D[i][j], D[i][k] + D[k][j])
```

Complexity:

```
Time: O(V³)
Space: O(V²)
```

If:

```
D[i][i] < 0
```

A **negative cycle exists**.

---

## Q66. What is the Single Source Shortest Path (SSSP) problem? [Easy]

**Answer**

SSSP finds the shortest path from **one source vertex to all others**.

Algorithms:

* Dijkstra
* Bellman-Ford
* BFS (for unweighted graphs)

Applications:

* GPS navigation
* Network routing
* Logistics optimization

---

## Q67. What is Dijkstra's algorithm? [Easy]

**Answer**

Dijkstra finds shortest paths in graphs with **non-negative edge weights**.

Steps:

1. Initialize distances
2. Use priority queue
3. Extract minimum distance vertex
4. Relax edges
5. Update distances

Complexity:

```
O((V + E) log V)
```

---

## Q68. What is Bellman–Ford algorithm? [Medium]

**Answer**

Bellman–Ford handles **negative edge weights**.

Steps:

Relax all edges **V−1 times**.

```
if dist[u] + w < dist[v]
update dist[v]
```

Detects **negative cycles** in the graph.

Time complexity:

```
O(VE)
```

---

## Q69. What is dynamic programming and how does it differ from greedy? [Medium]

**Answer**

Dynamic Programming solves problems by **breaking them into overlapping subproblems**.

Properties:

* Optimal substructure
* Overlapping subproblems

Greedy algorithms:

* Make local optimal choices
* Faster but not always optimal

Example:

* Floyd–Warshall → DP
* Dijkstra → Greedy

---

## Q70. What is the general method of dynamic programming? [Medium]

**Answer**

Steps in dynamic programming:

1. Define optimal solution structure
2. Recursively define subproblems
3. Compute solutions bottom-up
4. Construct final solution
---

