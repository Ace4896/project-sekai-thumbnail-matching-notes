# Project Sekai - Thumbnail Matching Notes

Notes on extracting and matching Project Sekai card thumbnails. 

## Usage

In this folder are various Jupyter notebooks outlining my attempts at extracting and matching card thumbnails:

- **Thumbnail Extraction**
  - [`character-box`](./character-box.ipynb)
    - Getting the character box from a screenshot of the character list
    - This step helps narrow down the search for thumbnails, as it filters out most of the menu controls
  - [`thumbnail-extraction`](./thumbnail-extraction.ipynb)
    - Extracting individual card thumbnails from the character list
- **Thumbnail Matching**
  - [`orb-feature-matching`](./orb-feature-matching.ipynb)
    - This approach involves computing ORB Features and performing brute-force matching of features
    - While this would be the most accurate, it's probably too slow for the usecase in mind (importing of cards from a screenshot)
    - I also haven't figured out a way to measure the "similarity" between the feature descriptors
  - [`hsv-histogram`](./hsv-histogram.ipynb)
    - This approach involves generating normalised colour histograms from HSV channels and comparing similarity
    - The matching speed is good, even with a linear search
    - However, the histograms are quite large, so storage may be an issue when more thumbnails are added
  - [`image-hashing`](./image-hashing.ipynb)
    - This approach involves generating image hashes from the thumbnails and comparing the distance between hashes
    - The matching speed is better than the histogram method, without a big sacrifice in accuracy
    - The hashes are just 64-bit integers, so storage is very simple

To run these notebooks:

- Install Python 3.11 or higher (may work on older versions, but not sure if it'll work)
- [Create a virtual environment and activate it](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment)
- Install dependencies: `pip install -r requirements.txt`
- Run `jupyter notebook`
