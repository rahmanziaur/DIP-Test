# Image-Processing-Tutorials
In This Repository, we add all the complete tutorial series on Image Processing and Computer Vision with complete Code and Theory. Video lectures are also available - https://www.youtube.com/channel/UCpWIxCtUo2IHh9d3fiyMaJw/playlists

https://colab.research.google.com/drive/1Se2OFSL8HtthdY5hoShGgNb17QtkPZxU


Digital Image and Speech Processing
Lab Viva Question Bank
Part A: Digital Image Processing  |  Part B: Speech Processing & Algorithms



70 Questions  |  Easy & Medium Difficulty
Undergrad Level  |  All Topics Covered

Part A: Digital Image Processing
Topics: Fundamentals, Color Models, Enhancement, Transforms, Segmentation, Compression
FUNDAMENTALS
Q1. What is digital image processing?  [Easy]
Answer: Digital image processing refers to the manipulation of images using digital computers. It involves applying algorithms to acquire, enhance, compress, restore, and analyze images in digital form (represented as a 2D array of pixels).
Q2. What is a pixel and how is an image represented digitally?  [Easy]
Answer: A pixel (picture element) is the smallest unit of a digital image. A digital image is represented as a 2D matrix f(x,y) where x and y are spatial coordinates and the value at each point represents the intensity (gray level or color). For an M×N image, the matrix has M rows and N columns.
Q3. What is image sampling and quantization?  [Easy]
Answer: Sampling is the process of converting a continuous spatial image into a discrete grid of pixels — deciding how many pixels to use. Quantization is the process of mapping the continuous range of intensity values into a finite number of discrete levels (e.g., 256 levels for 8-bit images). Together they determine the digital resolution of the image.
Q4. What are the basic relationships between pixels?  [Easy]
Answer: Key pixel relationships include: (1) Neighbors — 4-neighbors (N,S,E,W), diagonal neighbors, and 8-neighbors. (2) Adjacency — pixels are adjacent if they are neighbors and satisfy a gray-level condition. (3) Connectivity — a path exists between two pixels through adjacent pixels. (4) Distance measures — Euclidean, city-block (D4), and chessboard (D8) distances.
Q5. What is the difference between 4-connectivity and 8-connectivity?  [Easy]
Answer: In 4-connectivity, a pixel is connected only to its four horizontal and vertical neighbors. In 8-connectivity, a pixel is connected to all eight surrounding neighbors (including diagonals). 8-connectivity is more general and commonly used in image segmentation and region labeling.
Q6. What is spatial resolution and gray-level resolution?  [Medium]
Answer: Spatial resolution is the smallest discernible detail in an image, determined by the number of pixels (e.g., 512x512). Gray-level resolution refers to the number of distinct intensity levels, typically a power of 2 (e.g., 8-bit gives 256 levels). Higher resolution in both dimensions generally improves perceived image quality.
Q7. What is aliasing in image sampling?  [Medium]
Answer: Aliasing occurs when the sampling rate is insufficient to capture the highest frequency components of an image, causing high-frequency details to be misrepresented as lower frequencies. The Nyquist theorem states the sampling rate must be at least twice the highest frequency present to avoid aliasing. Anti-aliasing filters (low-pass) are applied before sampling.
COLOR MODELS
Q8. What is the RGB color model?  [Easy]
Answer: RGB (Red, Green, Blue) is an additive color model where colors are formed by combining red, green, and blue light. Each channel typically has values 0-255. White is (255,255,255) and black is (0,0,0). It is the primary model used in displays and digital cameras.
Q9. What is the HSV color model and its components?  [Easy]
Answer: HSV stands for Hue, Saturation, and Value. Hue (H) represents the color type (0-360 degrees), Saturation (S) represents color purity/richness (0-1), and Value (V) represents brightness (0-1). HSV is more intuitive for human color selection than RGB.
Q10. What is the CMY color model and where is it used?  [Easy]
Answer: CMY (Cyan, Magenta, Yellow) is a subtractive color model used in printing. Colors are formed by subtracting from white. The conversion from RGB is: C = 1-R, M = 1-G, Y = 1-B (with values normalized 0-1). CMYK adds a black (K) channel to improve print quality and reduce ink cost.
Q11. What is the YIQ color model?  [Medium]
Answer: YIQ is a color model used in NTSC television broadcasting. Y represents luminance (brightness), I (In-phase) and Q (Quadrature) represent chrominance (color information). It separates luminance from chrominance, allowing backward compatibility with black-and-white TVs and efficient bandwidth allocation.
Q12. How do you convert from RGB to HSV?  [Medium]
Answer: Given R,G,B in [0,1], let MAX = max(R,G,B), MIN = min(R,G,B), delta = MAX-MIN. V = MAX. S = delta/MAX (if MAX not 0, else S=0). H is computed based on which channel is MAX: if R: H = 60*((G-B)/delta mod 6); if G: H = 60*((B-R)/delta + 2); if B: H = 60*((R-G)/delta + 4). H is normalized to [0, 360 degrees].
ENHANCEMENT
Q13. What is a gray level transformation?  [Easy]
Answer: A gray level transformation (also called point operation or intensity transformation) maps each pixel's intensity value to a new value using a function: s = T(r), where r is the input intensity and s is the output. Examples include image negative, thresholding, log transformation, and power-law (gamma) transformation.
Q14. What is histogram equalization?  [Easy]
Answer: Histogram equalization is a technique to enhance image contrast by redistributing pixel intensities so that the histogram becomes approximately uniform. The equalized intensity is computed as: s_k = (L-1) * sum(n_j/N) for j=0 to k, where n_j is the count of pixels with intensity j and N is total pixels.
Q15. What is the difference between spatial and frequency domain enhancement?  [Medium]
Answer: Spatial domain methods operate directly on pixel values using operations like convolution with masks (e.g., averaging, sharpening filters). Frequency domain methods transform the image (e.g., using DFT), modify frequency components (e.g., low-pass or high-pass filtering), then transform back. Frequency methods are more efficient for large kernels.
Q16. What are spatial operations used for image smoothing?  [Easy]
Answer: Spatial smoothing reduces noise and blurring. Common methods: (1) Mean/averaging filter — replaces each pixel with the average of its neighborhood. (2) Median filter — replaces with the median value, effective against salt-and-pepper noise without blurring edges. (3) Gaussian filter — weighted average using a Gaussian kernel.
Q17. What is image sharpening and how is it achieved?  [Medium]
Answer: Image sharpening enhances edges and fine details. It is achieved by adding high-frequency components back to the image. Techniques include: (1) Laplacian filter — second-order derivative operator that highlights edges. (2) Unsharp masking — subtract a blurred version from the original. (3) High-boost filtering: f_hb = A*f - f_smooth.
Q18. What is multispectral image enhancement?  [Medium]
Answer: Multispectral image enhancement processes images captured across multiple spectral bands (e.g., satellite images with visible, NIR, thermal bands). Enhancement techniques are applied per band or across bands to improve color representation, contrast, and feature visibility. Principal Component Analysis (PCA) is commonly used to decorrelate bands.
TRANSFORMS
Q19. What is the Discrete Fourier Transform (DFT) and its significance?  [Medium]
Answer: The DFT converts a spatial-domain image into its frequency-domain representation. It reveals frequency content: low frequencies correspond to slow intensity changes (background), high frequencies to edges and noise. The Fast Fourier Transform (FFT) computes DFT efficiently in O(N log N). It is the basis for frequency-domain filtering and analysis.
Q20. What is the Discrete Cosine Transform (DCT)?  [Easy]
Answer: The DCT expresses a finite sequence of data as a sum of cosine functions. It is widely used in image compression (JPEG) because it compacts energy into fewer coefficients. The 2D DCT is applied to 8x8 image blocks. Unlike DFT, DCT uses only real numbers and has better energy compaction properties.
Q21. What is the Haar transform?  [Medium]
Answer: The Haar transform is the simplest wavelet transform. It uses a set of Haar basis functions (step functions) to decompose a signal into averages and differences. It is computationally efficient, requires no multiplications, and is used in image compression and feature extraction. It captures both frequency and spatial location information.
Q22. What is a Wavelet transform and how does it differ from DFT?  [Medium]
Answer: The Wavelet transform represents a signal using scaled and shifted versions of a mother wavelet function, providing both time (spatial) and frequency information simultaneously — unlike DFT which only provides frequency information. This multi-resolution property makes wavelets ideal for analyzing images with localized features, transients, and edges.
Q23. What is the convolution theorem in the context of image processing?  [Medium]
Answer: The convolution theorem states that convolution in the spatial domain is equivalent to multiplication in the frequency domain: f(x,y) * h(x,y) corresponds to F(u,v)*H(u,v). This means filtering can be done by multiplying the DFTs of the image and filter, then taking the inverse DFT — often more efficient than direct spatial convolution for large filters.
SEGMENTATION & FEATURES
Q24. What is image segmentation?  [Easy]
Answer: Image segmentation is the process of partitioning an image into meaningful regions or segments based on characteristics like color, intensity, or texture. The goal is to simplify or change the representation for easier analysis. Methods include thresholding, edge-based segmentation, region growing, and clustering (k-means).
Q25. What is edge detection and why is it important?  [Easy]
Answer: Edge detection identifies sharp changes in intensity that mark boundaries between objects. Edges carry important structural information. Common operators: (1) Sobel — computes gradient in x and y directions. (2) Prewitt — similar to Sobel. (3) Canny — multi-step: smoothing, gradient, non-maximum suppression, hysteresis thresholding. Canny is considered optimal.
Q26. What is the Canny edge detector and its steps?  [Medium]
Answer: The Canny edge detector involves: (1) Gaussian smoothing to reduce noise. (2) Computing gradient magnitude and direction using Sobel operators. (3) Non-maximum suppression — thinning edges to 1-pixel width. (4) Double thresholding — classify edges as strong, weak, or non-edges. (5) Edge tracking by hysteresis — retain weak edges connected to strong edges.
Q27. What is region growing in image segmentation?  [Medium]
Answer: Region growing starts from seed pixels and iteratively adds neighboring pixels that satisfy a similarity criterion (e.g., gray-level difference within a threshold). The region grows until no more pixels can be added. It is simple and effective but sensitive to the choice of seed pixels and the similarity criterion.
Q28. What are spatial features used in image analysis?  [Medium]
Answer: Spatial features describe the structure and content of image regions. Common features include: area, perimeter, compactness, eccentricity, Euler number, moments (centroid, orientation), and texture descriptors (GLCM — Gray Level Co-occurrence Matrix). These features are used in classification, recognition, and retrieval.
COMPRESSION
Q29. What is image compression and why is it needed?  [Easy]
Answer: Image compression reduces the number of bits required to represent an image. It is needed to save storage space and reduce transmission bandwidth. Compression exploits spatial redundancy (similar neighboring pixels), spectral redundancy (correlations between color channels), and psychovisual redundancy (information less sensitive to human vision).
Q30. What is the difference between lossless and lossy compression?  [Easy]
Answer: Lossless compression reconstructs the exact original image (e.g., PNG, Huffman coding, LZW). No information is lost. Lossy compression discards some information that is less perceptible to human vision (e.g., JPEG), achieving much higher compression ratios at the cost of some quality degradation. The choice depends on the application.
Q31. How does JPEG compression work?  [Medium]
Answer: JPEG compression works in steps: (1) Convert RGB to YCbCr and downsample chroma. (2) Divide into 8x8 blocks. (3) Apply DCT to each block. (4) Quantize DCT coefficients — the lossy step; higher quantization means more compression. (5) Zigzag scan and run-length encode the coefficients. (6) Apply Huffman coding for lossless entropy coding.
Q32. What is predictive coding in image compression?  [Medium]
Answer: Predictive coding encodes the difference between the actual pixel value and its predicted value (based on neighboring pixels). Since differences tend to be small, they can be represented with fewer bits. DPCM (Differential Pulse Code Modulation) is a classic example. The predictor uses surrounding pixels to estimate the current pixel's value.
Q33. What is MPEG and how does it extend JPEG for video?  [Medium]
Answer: MPEG (Moving Picture Experts Group) is a standard for compressing video sequences. It exploits temporal redundancy between frames using motion compensation. Frames are classified as: I-frames (intra-coded, like JPEG), P-frames (predicted from previous frame), and B-frames (bi-directionally predicted). This dramatically reduces the data needed compared to compressing each frame independently.
Q34. What is Huffman coding?  [Easy]
Answer: Huffman coding is an entropy coding technique that assigns shorter bit codes to more frequent symbols. It builds a binary tree where frequent symbols get shorter paths (codes). It is lossless and produces optimal prefix-free codes. Used as the final step in JPEG compression after quantization and run-length encoding.
Q35. What is transform coding in image compression?  [Medium]
Answer: Transform coding converts the image from the spatial domain to a transform domain (e.g., DCT, DWT) where energy is concentrated in fewer coefficients. Most coefficients are near-zero and can be discarded (quantized to zero), achieving compression. The retained coefficients are quantized and entropy-coded. JPEG uses DCT-based transform coding.

Part B: Speech Processing & Algorithms
Topics: Phonetics, Signal Analysis, Features, Speech Recognition, Graph Algorithms
PHONETICS
Q36. What is articulatory phonetics?  [Easy]
Answer: Articulatory phonetics is the study of how speech sounds are physically produced by the human vocal tract. It examines the movements and positions of articulators — the tongue, lips, teeth, velum, and glottis — during speech production. It classifies sounds based on place of articulation, manner of articulation, and voicing.
Q37. What are the main components of the human vocal tract involved in speech production?  [Easy]
Answer: The vocal tract consists of: (1) Lungs — provide airstream. (2) Larynx/Glottis — contains the vocal folds; their vibration produces voiced sounds. (3) Pharynx — the throat cavity above the larynx. (4) Oral cavity — shaped by tongue, lips, jaw, and teeth. (5) Nasal cavity — coupled via the velum (soft palate). Resonances of these cavities shape the spectral characteristics of speech.
Q38. How are speech sounds classified?  [Easy]
Answer: Speech sounds are classified as: (1) Vowels — produced with open vocal tract, voiced, classified by tongue height (high/mid/low), tongue backness (front/central/back), and lip rounding. (2) Consonants — classified by place of articulation (bilabial, alveolar, velar, etc.), manner of articulation (stop, fricative, nasal, affricate, lateral), and voicing. (3) Semi-vowels/Glides — sounds like /w/ and /j/.
Q39. What is the difference between voiced and voiceless sounds?  [Easy]
Answer: Voiced sounds are produced when the vocal folds vibrate, creating a periodic excitation (e.g., vowels, /b/, /d/, /z/). Voiceless sounds are produced without vocal fold vibration; air passes through a stationary glottis creating turbulent or impulsive excitation (e.g., /p/, /t/, /s/). The presence or absence of voicing is a key distinguishing feature in many language phoneme pairs.
Q40. What is acoustic phonetics?  [Easy]
Answer: Acoustic phonetics studies the physical properties of speech sounds as sound waves. It analyzes attributes like fundamental frequency (F0), formant frequencies (resonance peaks of the vocal tract), intensity, duration, and spectral shape. Tools like spectrograms, FFT, and LPC analysis are used to measure and visualize these acoustic properties.
Q41. What are formants and why are they important?  [Medium]
Answer: Formants are the resonant frequencies of the vocal tract. They appear as dark bands on a spectrogram. F1 (first formant) is inversely related to vowel height; F2 is related to tongue backness. F1 and F2 together are sufficient to distinguish most vowels. Formants carry the essential phonemic information that allows listeners to identify speech sounds. LPC analysis is commonly used to estimate formant frequencies.
Q42. What is the source-filter model of speech production?  [Medium]
Answer: The source-filter model represents speech production as the convolution of a source signal and a vocal tract filter. For voiced speech: the source is the periodic glottal pulse train (fundamental frequency F0); for unvoiced: it is broadband noise. The filter represents the acoustic resonances (formants) of the vocal tract shape. The output speech s(t) = source(t) * vocal tract filter. This model underlies LPC and many speech analysis techniques.
SIGNAL ANALYSIS
Q43. What is the Short-Time Fourier Transform (STFT) and why is it used in speech?  [Easy]
Answer: The STFT divides a speech signal into short overlapping frames (typically 20-30 ms) and applies the Fourier Transform to each frame. This gives a time-varying spectral representation. It is used because speech is non-stationary — its spectral content changes over time. The result is a spectrogram (time vs. frequency vs. magnitude), which is fundamental to speech analysis and recognition.
Q44. What is a spectrogram?  [Easy]
Answer: A spectrogram is a 2D visualization of a speech signal showing how the frequency content varies over time. The x-axis is time, the y-axis is frequency, and intensity (darkness/color) represents magnitude at each time-frequency point. It is computed using the STFT. Narrowband spectrograms show detailed frequency resolution (formant structure); wideband spectrograms show detailed time resolution (glottal pulses).
Q45. What is the role of windowing in STFT?  [Medium]
Answer: Windowing multiplies each frame of speech by a window function (e.g., Hamming, Hanning) before computing the FFT. This reduces spectral leakage — artifacts caused by the assumption that the signal repeats periodically outside the frame. The Hamming window w(n) = 0.54 - 0.46*cos(2*pi*n/(N-1)) is commonly used in speech processing for its good sidelobe suppression.
Q46. What are filters in the context of speech processing?  [Medium]
Answer: Filters modify the frequency content of a signal. In speech processing: (1) Pre-emphasis filter — a high-pass filter applied before analysis to boost high frequencies and compensate for the spectral tilt of the glottal source (H(z) = 1 - 0.97*z^-1). (2) Analysis filters — filterbanks (mel, bark scale) that decompose speech into frequency bands. (3) Synthesis filters — used in vocoders and LPC to reconstruct speech.
FEATURES
Q47. What are features in speech processing?  [Easy]
Answer: Features are compact numerical representations of speech that capture relevant acoustic information for a task (recognition, speaker ID, etc.). Good features should be: discriminative (distinguish between classes), robust to noise, and compact. Common features include MFCCs (Mel-Frequency Cepstral Coefficients), LPC coefficients, PLP coefficients, energy, and zero-crossing rate.
Q48. What are MFCCs and how are they computed?  [Easy]
Answer: MFCCs (Mel-Frequency Cepstral Coefficients) are the most widely used speech features. Computation steps: (1) Pre-emphasis. (2) Frame and window the signal. (3) Compute FFT. (4) Apply mel-scale filterbank (typically 26 filters). (5) Take log of filterbank energies. (6) Apply Discrete Cosine Transform (DCT). Typically 12-13 coefficients are used, plus delta and delta-delta for dynamic features.
Q49. What is the mel scale and why is it used?  [Easy]
Answer: The mel scale is a perceptual frequency scale where equal distances correspond to perceptually equal pitch differences for humans. It is approximately linear below 1 kHz and logarithmic above. The conversion is: mel = 2595 * log10(1 + f/700). Mel-scale filterbanks mimic the human auditory system's frequency resolution, making MFCCs perceptually meaningful and robust for speech recognition.
Q50. What are LPC coefficients?  [Medium]
Answer: LPC (Linear Predictive Coding) coefficients model the vocal tract as an all-pole filter. The current sample is predicted as a linear combination of past samples: s(n) = sum(a_k * s(n-k)). The predictor coefficients are the LPC coefficients. They compactly represent the spectral envelope (formant structure) of speech. Estimated by minimizing mean squared prediction error using the autocorrelation method and Levinson-Durbin algorithm.
Q51. What are PLP coefficients?  [Medium]
Answer: PLP (Perceptual Linear Prediction) coefficients combine the perceptual properties of auditory models with the compactness of LPC. Steps: (1) Compute the power spectrum. (2) Apply Bark-scale filterbank. (3) Apply equal-loudness curve weighting. (4) Apply cubic root compression. (5) Fit an autoregressive model (like LPC). PLP is more robust to speaker variation than MFCCs and models the auditory system more accurately.
Q52. What is the log spectral distance measure?  [Medium]
Answer: Log spectral distance (LSD) measures the difference between two spectral envelopes in the log domain. It is a perceptually meaningful distortion measure since the human auditory system responds to loudness on a logarithmic scale. It is used to compare LPC models and evaluate speech coding quality. LSD = sqrt[(1/2*pi) * integral(log P1(w) - log P2(w))^2 dw].
Q53. What are cepstral distances and why are they preferred?  [Medium]
Answer: Cepstral distance measures distortion in the cepstral domain. The cepstrum is the inverse Fourier transform of the log spectrum. Cepstral distance: CD = sqrt[sum(c1(n) - c2(n))^2]. It is preferred because: (1) Cepstral coefficients are approximately uncorrelated, simplifying distance computation. (2) It is equivalent to log spectral distance under certain conditions. (3) It is computationally efficient and directly relates to perceptual quality.
Q54. What is Dynamic Time Warping (DTW)?  [Medium]
Answer: DTW is a pattern comparison technique that aligns two time series by warping the time axis to find the optimal alignment that minimizes the total distance. It handles temporal variability in speech (different speakers saying the same word at different speeds). The DTW distance is the minimum cumulative distance along the optimal warping path, computed using dynamic programming.
SPEECH RECOGNITION
Q55. What is a large vocabulary continuous speech recognition (LVCSR) system?  [Easy]
Answer: An LVCSR system automatically converts continuous speech to text with a vocabulary of thousands to hundreds of thousands of words. It must handle co-articulation (sounds influencing neighbors), variability across speakers, and language complexity. Modern systems use deep neural networks for acoustic modeling, n-gram or neural language models, and beam search decoding.
Q56. What are the main components of a speech recognition system?  [Easy]
Answer: A speech recognition system consists of: (1) Feature extraction — compute MFCCs or filterbank features from the audio. (2) Acoustic model — models the relationship between acoustic features and phonemes (traditionally HMM-GMM, now DNN/RNN/Transformer). (3) Pronunciation lexicon — maps words to phoneme sequences. (4) Language model — assigns probabilities to word sequences. (5) Decoder — combines all three to find the most likely word sequence.
Q57. What is a Hidden Markov Model (HMM) in speech recognition?  [Medium]
Answer: An HMM models speech as a sequence of hidden states (phoneme sub-units) emitting observable features. For speech: states represent phoneme segments, transitions model temporal dynamics, and emission distributions (GMM or DNN) model the acoustic features. Each phoneme has a left-to-right HMM. Recognition finds the state sequence that maximizes the observation probability using the Viterbi algorithm.
Q58. What is speaker recognition and how does it differ from speech recognition?  [Easy]
Answer: Speaker recognition identifies or verifies who is speaking, not what is being said. It has two sub-tasks: (1) Speaker verification — confirm whether a speaker is who they claim to be (1:1 matching). (2) Speaker identification — determine which of N known speakers is speaking (1:N matching). Features like MFCCs, i-vectors, and x-vectors (deep learning embeddings) capture speaker-specific characteristics rather than linguistic content.
Q59. What is pitch estimation in speech?  [Medium]
Answer: Pitch (F0) is the fundamental frequency of voiced speech, perceived as the tone or prosody of the voice. It ranges from about 80-300 Hz (lower for males, higher for females and children). Pitch estimation methods include: (1) Autocorrelation — find the lag with the highest correlation. (2) AMDF (Average Magnitude Difference Function). (3) Cepstrum — the peak in the quefrency domain corresponds to 1/F0. Pitch is used in prosody analysis, speaker recognition, and voice conversion.
Q60. What is speech restoration?  [Medium]
Answer: Speech restoration (enhancement) aims to recover clean speech from a degraded signal corrupted by noise, reverberation, or channel distortion. Techniques include: (1) Spectral subtraction — subtract estimated noise spectrum from noisy speech spectrum. (2) Wiener filtering — statistically optimal linear filter. (3) Deep learning methods — train neural networks to map noisy to clean speech. Applications include hearing aids, telephony, and ASR front-ends.
Q61. What is speaker separation (cocktail party problem)?  [Medium]
Answer: Speaker separation aims to isolate individual speakers from a mixture of simultaneous voices. Approaches include: (1) Beamforming — use microphone arrays to focus on a spatial direction. (2) ICA (Independent Component Analysis) — statistically separate mixed sources. (3) Deep learning — models like deep clustering, permutation-invariant training (PIT), and Conv-TasNet directly separate waveforms using neural networks.
GRAPH ALGORITHMS
Q62. What is a greedy algorithm and give an example?  [Easy]
Answer: A greedy algorithm makes the locally optimal choice at each step, hoping to find a global optimum. It never reconsiders past choices. Examples: (1) Dijkstra's algorithm for shortest paths — always picks the unvisited vertex with the smallest known distance. (2) Activity selection — always pick the activity that finishes earliest. Greedy algorithms are efficient but do not always give the optimal solution for every problem.
Q63. What is the multistage graph problem?  [Medium]
Answer: A multistage graph is a directed graph whose vertices are partitioned into k stages such that edges only go from stage i to stage i+1. The multistage graph problem finds the minimum-cost path from a source (stage 1) to a sink (stage k). It is solved using dynamic programming: cost(v) = min over successors u of [c(v,u) + cost(u)], computed backward from the sink. It models pipeline-style decision problems.
Q64. What is the All Pairs Shortest Paths (APSP) problem?  [Medium]
Answer: The APSP problem finds the shortest path between every pair of vertices in a weighted graph. The classic algorithm is Floyd-Warshall: it iteratively considers each vertex k as an intermediate node and updates d[i][j] = min(d[i][j], d[i][k] + d[k][j]). Its time complexity is O(V^3) and it handles negative edge weights (but not negative cycles). The result is a matrix of shortest distances.
Q65. What is the Floyd-Warshall algorithm?  [Medium]
Answer: Floyd-Warshall computes all-pairs shortest paths using dynamic programming. It maintains a distance matrix D where D[i][j] is the shortest known path from i to j. For each intermediate vertex k (1 to V): for all pairs i,j: D[i][j] = min(D[i][j], D[i][k] + D[k][j]). After V iterations the matrix contains the shortest paths. Time: O(V^3), Space: O(V^2). If D[i][i] < 0, a negative cycle exists.
Q66. What is the Single Source Shortest Path (SSSP) problem?  [Easy]
Answer: The SSSP problem finds the shortest path from one source vertex to all other vertices in a weighted graph. Key algorithms: (1) Dijkstra's algorithm — works for non-negative edge weights, O((V+E)log V) with a priority queue. (2) Bellman-Ford — handles negative edges, detects negative cycles, O(VE). (3) BFS — for unweighted graphs, O(V+E). SSSP is foundational in navigation, routing, and network analysis.
Q67. What is Dijkstra's algorithm and how does it work?  [Easy]
Answer: Dijkstra's algorithm finds the shortest path from a source to all vertices in a graph with non-negative weights. Steps: (1) Initialize dist[source]=0, dist[all others]=infinity. (2) Use a min-priority queue. (3) Extract the vertex u with minimum distance. (4) For each neighbor v of u: if dist[u] + w(u,v) < dist[v], update dist[v] (relaxation). (5) Repeat until all vertices are processed. Time: O((V+E)log V) with a binary heap.
Q68. What is the Bellman-Ford algorithm and when is it preferred over Dijkstra?  [Medium]
Answer: Bellman-Ford computes single-source shortest paths and handles negative edge weights. It relaxes all edges V-1 times: for each edge (u,v,w): if dist[u]+w < dist[v], update dist[v]. A V-th pass detects negative cycles. Time: O(VE). Preferred over Dijkstra when: (1) negative edge weights exist, (2) negative cycle detection is needed, (3) the graph is sparse and distributed (e.g., routing protocols like RIP).
Q69. What is dynamic programming and how does it differ from greedy?  [Medium]
Answer: Dynamic programming (DP) solves problems by breaking them into overlapping subproblems, solving each once, and storing results (memoization/tabulation). It guarantees optimal solutions. Greedy makes locally optimal choices without reconsidering past decisions — faster but only works for problems with the greedy-choice property. Example: Floyd-Warshall is DP; Dijkstra (with non-negative weights) is greedy.
Q70. What is the general method of dynamic programming?  [Medium]
Answer: The general DP method involves: (1) Characterize the structure of an optimal solution. (2) Recursively define the value of an optimal solution in terms of smaller subproblems. (3) Compute the value bottom-up (or top-down with memoization). (4) Construct the optimal solution from stored information. Key properties needed: optimal substructure and overlapping subproblems (same subproblems recur).

