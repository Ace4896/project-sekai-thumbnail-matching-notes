# Project Sekai - Thumbnail Matcher

A test app for matching Project Sekai card thumbnails.

## Usage

In this folder are various Jupyter notebooks outlining some approaches to matching thumbnails against reference images:

- [`colour-histogram`](.\colour-histogram.ipynb)
  - This approach involves generating normalised colour histograms and comparing similarity
  - This works well after adding a mask (i.e. cropping the thumbnails) to a fixed region
- [`orb-feature-matching`](.\orb-feature-matching.ipynb)
  - This approach involves computing ORB Features and performing brute-force matching of features
  - While this would be the most accurate, it's probably too slow for the usecase in mind (importing of cards from a screenshot)
  - I also haven't figured out a way to measure the "similarity" between the feature descriptors

To run these notebooks:

- Install Python 3.11 or higher (may work on older versions, but not sure if it'll work)
- [Create a virtual environment and activate it](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment)
- Install dependencies: `pip install -r requirements.txt`
- Run `jupyter notebook`
