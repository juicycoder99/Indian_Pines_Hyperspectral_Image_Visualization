# CS503 — Data Visualization — HW3

Coursework for **Data Visualization (CS503)**, Department of Computer Science, Bishop's University.

## Hyperspectral data visualization — Indian Pines

Visualizing and reducing the **Indian Pines** hyperspectral scene (AVIRIS sensor): a
145 × 145 image with 200 spectral bands and 16 labelled land-cover classes.

The solution is in [`HW3.ipynb`](HW3.ipynb).

## What the notebook covers

1. Load the hyperspectral data cube (`Indian_pines_corrected.mat`).
2. Compose and display a false-color image from three bands.
3. Load and display the ground-truth reference image (`Indian_pines_gt.mat`).
4. Class distribution as a bar plot (background class excluded).
5. Overlay the ground truth as a colored mask on the false-color image, with a class legend.
6. Select 1% of the pixels of each class and plot the mean spectral signatures.
7. Apply **PCA** and **t-SNE** to the cube and show the scatter of the first two components,
   colored by class.
8. Reconstruct the scene as an image from the first PCA component and from the two t-SNE components.

## Notes

- PCA's first two components explain about 92% of the spectral variance (PC1 ≈ 68%, PC2 ≈ 24%).
- t-SNE is run on the first 30 PCA dimensions to stay tractable over the ~21,000 pixels.

## Running it

```bash
pip install numpy scipy matplotlib scikit-learn spectral tqdm
jupyter notebook HW3.ipynb
```

## Files

| File | Description |
|------|-------------|
| `HW3.ipynb` | Full solution |
| `HW3.pdf` | Assignment description |
| `Indian_pines_corrected.mat` | Hyperspectral data cube (145 × 145 × 200) |
| `Indian_pines_gt.mat` | Ground-truth class labels |
