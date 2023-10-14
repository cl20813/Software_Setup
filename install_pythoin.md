# MSDS (Professor Gemma Moran and Professor Min Xu)

## Installation
Download Anaconda [here](https://www.anaconda.com/download).
(Note: there are a variety of different python distributions; for statistics and machine learning, we recommend Anaconda.)

### Creating an environment for MSDS-534
We recommend creating a virtual environment for your MSDS-534 coding projects.
1. Open Terminal
2. Create an environment called `msds534` using `conda` with the command:
   ```conda create --name msds534```
3. To install packages in your environment, first activate your environment:
   ```conda activate msds534```
4. Then, install the following packages using the command:
   ```conda install numpy pandas matplotlib seaborn scikit-learn```
5. Install PyTorch by running the appropriate command from [here](https://pytorch.org) (for macOS, the command is: `conda install pytorch::pytorch torchvision torchaudio -c pytorch`
6. To exit your environment:
   ```conda deactivate```

Here is a helpful [cheatsheet](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) for `conda` environment commands.
