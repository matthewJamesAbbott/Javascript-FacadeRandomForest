# Javascript-FacadeRandomForest

This repository contains a browser-based Random Forest implementation in JavaScript, featuring a facaded API for transparent inspection and manipulation of per-tree and per-node properties.  
It is intended for technical exploration, learning, and demonstration of Random Forests with no hidden internals—enabling direct visualization and editing of model state.

---

## Table of Contents

- [About](#about)
- [Features](#features)
- [Getting Started](#getting-started)
- [Basic Example](#basic-example)
- [Facade API](#facade-api)
- [Usage Notes](#usage-notes)
- [License](#license)

---

## About

Javascript-FacadeRandomForest provides a fully configurable Random Forest classifier in the web browser.  
You can adjust forest hyperparameters, inspect or modify individual trees and nodes at runtime, and monitor training analytics.  
The facade system makes every split, feature selection, node threshold, prediction, and forest-level metric accessible through the web interface.

---

## Features

- Forest configuration:
  - Number of trees, tree depth, min samples per split, max features per split
  - Support for Gini impurity or entropy splitting criteria
  - Bootstrap sampling and out-of-bag (OOB) evaluation options
- Training options:
  - Train/validation split configuration
  - Adjustable maximum tree depth, forest size, and feature subset strategy (`sqrt`, `log2`, `all`)
- Data handling:
  - Upload training data from CSV or paste as plain text
  - Synthetic data generator for binary or multi-class tasks
  - Visual display of train/test partitioning and shuffling
- Monitoring:
  - Live accuracy, precision, recall, and OOB error reporting
  - Single-tree and full-forest visualization
  - Save/load trained forest models as JSON files
- Facade API:
  - Inspect any tree or node: split features, thresholds, samples, impurity
  - View and traverse tree structure interactively
  - Modify node thresholds, force feature splits, prune or grow subtrees at runtime
  - Review feature importances and per-class statistics
  - Edit key parameters for any tree or node on the fly
- Inference:
  - Manual test vector input and prediction, with breakdown of vote contributions

---

## Getting Started

### Requirements

- A modern web browser (Chrome, Firefox, Edge, Safari, etc.)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/matthewJamesAbbott/Javascript-FacadeRandomForest.git
    ```
2. Open `index.html` with your web browser.

_No additional installation or server required._

---

## Basic Example

To run a 3-class classification demo:

1. Open `index.html`
2. Set the forest parameters:
    - Number of Trees: `25`
    - Max Depth: `6`
    - Min Samples Split: `4`
    - Max Features: `sqrt`
    - Splitting Criterion: `Gini`
    - Bootstrap: `Enabled`
3. Generate synthetic dataset (default: 500 samples/class)
4. Under **Training Configuration**:
    - Validation Split: `0.2` (for 80/20 train/test)
5. Click **Train Forest**
6. Use **Facade API Explorer** to inspect tree/node splits, paths, thresholds, statistics, or modify parameters live.

---

## Facade API

The façade API (in the web interface) allows comprehensive inspection and editing of:

- Tree and node properties: split feature, threshold, impurity, samples, predictions at any node
- Visualization of branch decisions for every tree
- Out-of-bag vote breakdown and accuracy per tree
- Feature importance, per-class metrics, confusion matrix
- Edit trees: modify thresholds, adjust splits, prune or add new nodes during runtime
- Export/import the entire forest or a single tree as JSON

All actions and results are displayed in the output panel, and most model manipulations are live—no need to halt training or inference.

---

## Usage Notes

- Best suited for moderate-sized forests (5–100 trees, 3–10 depth) for browser speed.
- Data processing and model training are entirely client-side—your data is not uploaded.
- Built-in synthetic data generation is for demo, not benchmarking or real-world evaluation.
- Saved forests are plain JSON, reloadable via the same interface.

---

## License

MIT License.  
You are free to use, modify, and distribute for any purpose.

---

## Demo Link

https://javascript-facade-randomforest.vercel.app/
