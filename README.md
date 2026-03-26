# Wall-E Waste Detection Training

This repository contains experiments for training and comparing YOLO-based models for waste detection.

The project is organized around:
- dataset preparation and cleaned dataset versions
- YOLO training runs and saved weights
- generated training and comparison reports
- a notebook for training workflows

## Project Structure

- `train_yolo.ipynb`: main notebook used to train and evaluate models.
- `dataset/`: local datasets (ignored by Git).
- `runs/`: training outputs (metrics, weights, logs).
- `reports/`: generated markdown reports for model performance comparisons.
- `yolo26n.pt`: base YOLO checkpoint used for training.

## Environment Setup (Conda)

This project now provides a full Conda environment file: `environment.yml`. You should use a Unix Kernel.

### 1. Create the environment from file

```bash
conda env create -f environment.yml
```

### 2. Activate the environment

```bash
conda activate yolo_conda
```

### 3. Update the environment after changes (optional)

If `environment.yml` is updated, synchronize your local environment with:

```bash
conda env update -f environment.yml --prune
```

### 4. Important packages included

The exported environment already includes the required packages, including:
- `ultralytics`
- `tensorflow-base`
- `kaggle-environments`

If you need to install them manually in another environment, use:

```bash
conda install -c conda-forge ultralytics -y
conda install conda-forge::tensorflow-base -y
conda install conda-forge::kaggle-environments -y
```

### 5. Install additional dependencies (optional)

For extra experimentation tools, install additional packages with Conda as needed, for example:

```bash
conda install -c conda-forge jupyterlab -y
```

## Run the Training Notebook

```bash
jupyter lab
```

Then open `train_yolo.ipynb` and run the cells.

## Git Notes

Datasets are intentionally excluded from version control via `.gitignore`.

## Optional: Export Environment

To make experiments reproducible, you can export your environment:

```bash
conda env export --no-builds > environment.yml
```

Then recreate it later with:

```bash
conda env create -f environment.yml
```
