# MSC Cell Counting Pipeline

Automated pipeline for counting mesenchymal stem cells (MSCs) from brightfield microscopy images. 

## What this is

An end-to-end image analysis pipeline that takes raw brightfield TIFF images from a Cytation5 microscope and outputs per-image confluence (%) and cell count estimates. The pipeline was developed and applied to a dataset of 40 images covering three MSC sources (AD, BM, UC) across six timepoints (4–34h post-seeding).

## What to look at

- **`msc_cell_counting.ipynb`** — the main analysis notebook. Contains the full pipeline, all parameter tuning visualisations, results, and the Cellpose comparison. Start here.
- **`results_classical_cv.csv`** — per-image confluence and count outputs from the classical CV pipeline.
- **`results_cellpose.csv`** — per-image outputs from Cellpose (cyto2).

The written report (`Yuhyeon(Zoey)Kim_Multus_report.pdf`) covers methods, results, and next steps for an R&D science audience.

## Pipeline overview

1. Well boundary masking
2. Background correction (vignetting removal)
3. Adaptive thresholding
4. Watershed segmentation
5. Morphology filter (eccentricity + area)
6. QC flagging + no-growth detection

## Data

The raw image dataset is not included in this repository. Images were provided by Multus Bioscience and are not redistributed out of respect for data privacy.

## Dependencies

```
scikit-image
numpy
matplotlib
tifffile
cellpose
scipy
pandas
```

## Contact

Yuhyeon (Zoey) Kim: yuhyeon.z.kim@gmail.com