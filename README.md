# Automated Foot Measurement System Using YOLOv8 and Reference Coin | BRP-SizeMeasure

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.7%2B-blue)
![YOLOv8](https://img.shields.io/badge/YOLO-v8-orange)

A highly accurate automated foot measurement system leveraging YOLOv8 object detection, adaptive thresholding, and semantic segmentation. Uses a reference coin for scale calibration, achieving 0.05 cm measurement accuracy and 10 ms inference time. Validated through scientific research for medical, orthotic, and e-commerce applications.

This repository contains the codebase supporting the research paper: **"AUTOMATED FOOT MEASUREMENT USING YOLOv8 AND A REFERENCE COIN."**

## Keywords
`YOLOv8` `Foot Measurement` `Computer Vision` `Object Detection` `Semantic Segmentation` `E-commerce Virtual Fitting` `Diabetic Foot Screening` `Orthotics` `Reference Coin Calibration` `Python` `OpenCV` `BRP-SizeMeasure`

## Performance & Accuracy
* **Object Detection Model:** YOLOv8
* **Mean Average Precision (mAP):** 0.99
* **Inference Time:** ~10 ms
* **Measurement Accuracy:** 0.05 cm average error (0.02 cm standard deviation)

## Resources & Publications

* **Research Paper:** [Automated Foot Measurement Using YOLOv8 and a Reference Coin](https://thesesjournal.com/index.php/1/article/view/3058) (Spectrum of Engineering Sciences, Vol. 4 No. 5, 2026)
* **Dataset:** [Foot Measurement - Feet data](https://www.scidb.cn/en/detail?dataSetId=d318097f975940e2bb9be0ef9e946b7b) (ScienceDB, DOI: 10.57760/sciencedb.28004) - Includes 2,026 labeled foot images.

## Features
* **Background Removal:** Eliminates noise from the input image using semantic segmentation.
* **Object Detection:** Detects the foot and the reference coin using custom-trained YOLOv8 models.
* **Edge Detection & Measurement:** Applies adaptive thresholding and Canny edge detection to extract physical dimensions in centimeters.
* **PDF Report Generation:** Compiles marked images and calculated dimensions into a downloadable PDF report.

## Installation

1. Clone the repository:
```bash
   git clone [https://github.com/Xer0bit/BRP-SizeMeasure](https://github.com/Xer0bit/BRP-SizeMeasure)
   cd BRP-SizeMeasure

```

2. Create and activate a virtual environment (recommended):

```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate

```

3. Install required dependencies:

```bash
   pip install -r requirements.txt

```

## Usage

1. **Prepare Models:** Place the required pre-trained YOLOv8 `.pt` model files into the `models/` directory:

* `models/feet.pt`
* `models/coin.pt`

2. **Execute System:**

```python
   from image_processing import remove_background, detect_objects
   from pdf_report import generate_pdf_report

   original_image_path = 'path/to/image.jpg'
   output_pdf_path = 'path/to/report.pdf'

   # Process Image
   detection_results = detect_objects(remove_background(original_image_path))
   
   # Generate Report
   generate_pdf_report(detection_results, output_pdf_path, original_image_path)

```

## Academic Citation

If you utilize this codebase or dataset in your research, please cite:

```bibtex
@article{sameer2026automated,
  title={AUTOMATED FOOT MEASUREMENT USING YOLOv8 AND A REFERENCE COIN},
  author={Sameer, Muhammad and Nazir, Filzah and Fatima, Irum and Nadeem, Syeda Rysham},
  journal={Spectrum of Engineering Sciences},
  volume={4},
  number={5},
  pages={2751--2766},
  year={2026},
  url={[https://thesesjournal.com/index.php/1/article/view/3058](https://thesesjournal.com/index.php/1/article/view/3058)}
}

```

## Authors

* Muhammad Sameer
* Filzah Nazir
* Irum Fatima
* Syeda Rysham Nadeem

## License

Licensed under the [MIT License](https://www.google.com/search?q=LICENSE).

