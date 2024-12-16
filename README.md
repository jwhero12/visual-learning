# **Medical Image Analysis with SAM and Edge Detection**

## 📌 **Project Purpose and Objective**

This project aims to segment fine structures (e.g., retinal vessels) in medical images by independently evaluating **Segment Anything Model (SAM)** and **Edge Detection** techniques, as well as exploring the potential combination of these two approaches. The ultimate goal is to overcome the limitations of existing methods and improve the precision and efficiency of medical image analysis.

### **Key Challenges and Solutions**
- **SAM**: Struggles with segmenting structures that have low contrast or complex patterns.  
- **Edge Detection**: Effectively detects fine structures but is sensitive to noise.  

### **Project Overview**
1. **Segment Anything Model (SAM)**  
   - Utilizes a grid-based segmentation approach.  
   - Optimizes performance by tuning parameters and applying color inversion.  

2. **TEED Model-Based Edge Detection**  
   - Applies preprocessing techniques, such as CLAHE and Gaussian Blur, to reduce noise and enhance structure detection.  
   - Experiments with post-processing methods like Median and Bilateral Filtering.  

### **Expected Contribution**
This project analyzes the strengths and weaknesses of SAM and Edge Detection independently, evaluates their performance qualitatively and quantitatively, and explores their combined potential to enhance reliability and accuracy in medical image analysis.

---

## 🚀 **How to Start the Project**

### **2-1. Running SAM**
To be added soon.

### **2-2. Running TEED**
Follow the instructions below, or refer to `retina_edgedetection.ipynb`.
The TEED model is not currently included in the GitHub repository. Please refer to [TEED GitHub Repository](https://github.com/xavysp/TEED.git) for further details.

#### **1️⃣ Pre-requisites**
Clone the repository:
```bash
git clone https://github.com/xavysp/TEED.git
```
Install the required dependencies:
```bash
pip install thop
pip install kornia
```

#### **2️⃣ Preprocessing Steps**
The preprocessing pipeline involves the following steps:
1. **Gamma Correction**  
2. **Green Channel Extraction** → CLAHE → Gaussian Blur → Sharpening  
3. Repeated execution of Step 2.

#### **3️⃣ Execution**
- Place the target images in the `data` folder.  
- Run the following command:
   ```bash
   python TEED/main.py
   ```
- You can customize preprocessing and execution using `dataset.py` and `main.py`.

#### **4️⃣ Post-Processing**
Post-processing techniques include **Median Filtering**, **Bilateral Filtering**, and **Sharpening** to refine the results.

#### **5️⃣ Evaluation**
Performance is evaluated using the following metrics:
- **SSIM (Structural Similarity Index)**  
- **MSE (Mean Squared Error)**  
- **NCC (Normalized Cross-Correlation)**  
- **Pixel Overlap**

---

## 📊 **Evaluation Results**

The table below summarizes the evaluation results for **TEED** and various post-processing techniques.  

|               | **SSIM** | **MSE** | **Pixel Overlap** |
|---------------|---------:|--------:|------------------:|
| **TEED1**    | 0.748    | 19.0    | 0.500             |
| **TEED2**    | 0.774    | 17.4    | 0.526             |
| **TEED3**    | 0.766    | 18.2    | 0.294             |
|               |          |         |                   |
| **Median1**  | 0.809    | 15.4    | 0.541             |
| **Median2**  | 0.812    | **15.3** | **0.562**         |
| **Median3**  | **0.815** | 15.4    | 0.215             |
|               |          |         |                   |
| **Median, Bilateral 1** | 0.806 | 19.0 | 0.236          |
| **Median, Bilateral 2** | 0.808 | 19.2 | 0.245          |
| **Median, Bilateral 3** | 0.812 | 18.4 | 0.227          |
|               |          |         |                   |
| **Sharpening1** | 0.798  | 15.9    | 0.221             |
| **Sharpening2** | 0.799  | 15.9    | 0.227             |
| **Sharpening3** | 0.805  | 15.5    | 0.209             |

---

## 📚 **External Resources**
The TEED model is based on the following publication:

```
@InProceedings{Soria_2023teed,
    author    = {Soria, Xavier and Li, Yachuan and Rouhani, Mohammad and Sappa, Angel D.},
    title     = {Tiny and Efficient Model for the Edge Detection Generalization},
    booktitle = {Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV) Workshops},
    month     = {October},
    year      = {2023},
    pages     = {1364-1373}
}
```

---

## 🛠 **Project Structure**
```plaintext
├── data/                # Input data folder
├── TEED/
│   ├── main.py          # Main execution file
│   ├── dataset.py       # Dataset configuration
│   └── ...              # Additional code files
├── retina_edgedetection.ipynb  # Jupyter Notebook for TEED
└── README.md            # Project documentation
```

---

## 🤝 **Contributing**
- To contribute to this project, create an **Issue** or submit a **Pull Request**.  
- Feedback and suggestions are always welcome!

--- 

This format provides a clear and organized presentation of your project, evaluation results, and instructions. Let me know if you'd like further adjustments! 🚀
