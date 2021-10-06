# How to use Jupyter Notebooks in a Virtual Environment created with Anaconda (Brower and VS Code)
*Date: October 16, 2021*

## The Issue
You may have the following problem: "You trying to import packages in a new Jupyter Notebook in an environment created with Anaconda and when running the block you get in the output: ***ModuleNotFoundError: No module named 'package-name'*** ". This may happen even if you are 100% sure that the package is installed.

## What I know
- If you open Jupyter Notebooks from the "Anaconda Navigator" (even if you selected the correct environent) you'll have this problem. So **DON'T USE IT**
- This is Kernel related, there's an issue that's not allowing Jupyter to connect to your Environment

## How to Solve It

The following code needs to typed in "Anaconda Prompt" and the Anaconda Navigator needs to be closed

1. Switch to your Created environment (if you don't have one, ignore this)
```
conda activate "environment-name"
```
2. Make sure you have installed the following packages in your environment (or base installation if you havent created one)

```
conda install -c conda-forge notebook
conda install -c conda-forge nb_conda_kernels
conda install -c conda-forge jupyterlab
```
3. Open Jupyter Notebooks (in your browser) with
```
jupyter notebook
```
## How to Solve it if you want to use VS Code (Optional)

1. Make sure you have done Step 1 and 2 of the section before
2. Open VS Code in Anaconda Prompt using
```
code
```

    Note: If this step doesn't work you may need to revise that VS Code environmental variable is correctly set (beyond the scope of this document)

3. Press Ctrl+Sht+P (To Open the Command Palette) and search for "Notebook: Select Notebook Kernel"

    Make sure to select your correct Anaconda version ('base':conda) or ('environment-name':conda)  

4. Press Ctrl+Sht+P (To Open the Command Palette) and search for "Python: Select Interpreter"

    Make sure to select your correct Anaconda version ('base':conda) or ('environment-name':conda)
5. (Optional) If you have a environment, open a "Command Prompt Terminal". It should automatically write something like:
```
conda activate "environment-name"
```
   If it doesn't appear, you need to write it so that the name of your environment appears at the beginning of the command line

## Credits
Hope this helped. It took me a great number of hours to get it work
