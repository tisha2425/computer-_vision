## Xerox JBIG2 Compression Bug Study

This repository demonstrates how document image compression can preserve visual appearance while corrupting machine interpretation.

### Purpose

* Study effects of aggressive compression on binary documents.
* Expose mismatch between human perception and algorithmic reasoning.
* Reproduce failure patterns related to the Xerox JBIG2 incident.

---

## Task Overview

### Task 1. Binary Document Decomposition

* Grayscale document converted to binary using Otsu thresholding.
* Connected components extracted from binarized output.
* Noise filtered using area constraints.
* Character regions isolated for further analysis.

### Task 2. Character Similarity Grouping

* Visual similarity measured using pixel IoU and SSIM.
* Rule based decision applied to identify identical symbols.
* Greedy clustering used to group matching characters.
* Symbol reuse behavior simulated at document level.

### Task 3. Compression Metric Analysis

* JPEG compression applied at multiple quality levels.
* PSNR and SSIM computed for each version.
* Structural similarity observed to remain high.
* Pixel level error observed to increase rapidly.

### Task 4. Recognition Failure Measurement

* Simple geometric classifier applied to character regions.
* Predictions generated for original and compressed documents.
* Classification accuracy compared across versions.
* Compression induced misclassification identified.

### Task 5. Forensic Failure Visualization

* Misclassified regions highlighted on compressed document.
* Visual similarity contrasted with semantic corruption.
* Risk of silent document alteration demonstrated.

---

## Key Observations

* Visual quality does not guarantee logical correctness.
* SSIM aligns with human judgment, not semantic safety.
* Compression artifacts alter geometric features.
* Rule based OCR fails without visible warning.
* Symbol substitution creates critical document errors.

---

## Tools and Libraries

* Python
* OpenCV
* NumPy
* scikit-image
* Matplotlib

---

## Applications

* Document forensics
* OCR robustness evaluation
* Compression artifact analysis
* Security critical document validation

---

## Execution

* Provide a scanned text document image.
* Run the notebook sequentially.
* Observe metrics, grouping behavior, and failure regions.

---
## How to Run

* Clone the repository.
* Install dependencies.
* Add a document image.
* Run the notebook top to bottom.

## Conclusion

Compression optimized for storage can introduce semantic corruption without perceptual cues.
Document pipelines require validation beyond visual similarity metrics.

