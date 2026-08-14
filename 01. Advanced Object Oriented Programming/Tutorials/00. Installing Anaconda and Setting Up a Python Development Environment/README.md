# **Tutorial 00: Installing Anaconda and Setting Up a Python Development Environment**

### Overview

Before writing Python programs, it is important to set up a reliable development environment.

In this tutorial, you will learn how to install Anaconda, create your first Python environment, launch development tools, and verify that Python is working correctly.

Anaconda is one of the most widely used Python distributions for software development, data science, machine learning, artificial intelligence, and research projects. It bundles Python together with many commonly used libraries and tools, making setup much easier than installing everything manually.

## **Learning Objectives**

After completing this tutorial, you should be able to:

-- Understand what Anaconda is and why it is useful.

-- Install Anaconda on Windows, macOS, or Linux.

-- Launch Jupyter Notebook and Spyder.

-- Create and manage Python environments.

-- Verify a successful installation.

-- Run your first Python program.

# Why Use Anaconda?

When building AI and data-driven applications, developers often need numerous libraries such as:

```
NumPy
Pandas
Matplotlib
SciPy
Scikit-Learn
TensorFlow
PyTorch
```

Installing these packages individually can be time-consuming and may lead to dependency conflicts.

Anaconda simplifies the process by providing:

-- Python interpreter

-- Package manager

-- Environment management

-- Data science libraries

-- Notebook environment

-- Development tools

This makes it an excellent choice for beginners and professionals alike.

# What Is Included in Anaconda?

A standard Anaconda installation provides access to:

| Component        | Purpose                         |
| ---------------- | ------------------------------- |
| Python           | Programming language            |
| Conda            | Package and environment manager |
| Jupyter Notebook | Interactive coding environment  |
| JupyterLab       | Modern notebook interface       |
| Spyder           | Scientific Python IDE           |
| NumPy            | Numerical computing             |
| Pandas           | Data analysis                   |
| Matplotlib       | Data visualization              |
| Scikit-Learn     | Machine learning                |


# Anaconda vs Standard Python

| Feature                | Standard Python     | Anaconda      |
| ---------------------- | ------------------- | ------------- |
| Python Interpreter     | ✅                   | ✅             |
| Package Manager        | pip                 | conda + pip   |
| Scientific Libraries   | Manual Installation | Preconfigured |
| Environment Management | Limited             | Excellent     |
| Data Science Ready     | No                  | Yes           |
| Beginner Friendly      | Moderate            | High          |

For AI-related work, Anaconda is generally the more convenient option.

# **Step 1: Download Anaconda**

Visit the official Anaconda [website](https://www.anaconda.com/download), you may need to free signup/sign in to proceed, choose the installer that matches your operating system. Examples: Windows 64-bit, macOS, Linux. 

**Always download a recent Python 3.X version** unless a project specifically requires an older release. 

Follow the installation instructions. 

Choose the default installation location. 

**Advanced Options**
You may see options such as:
```
Add Anaconda to PATH
Register Anaconda as default Python
```
Recommended:

✅ Register Anaconda as default Python

⚠ Avoid modifying PATH unless you understand the implications.

**Complete Installation: Click ```Install```

# **Step 2: Verify Installation**
Open ```Anaconda Prompt```, then enter ```python --version```

Expected output: ```Python 3.x.x```

Next, check Conda: ```conda --version```, expected output: ```conda 24.x.x```

If both commands work, the installation was successful.

# **Step 3: Launching Jupyter Notebook***

Jupyter Notebook is one of the most popular tools for learning Python. It is a good idea to type your code in Jupyter Notebook as a learner. 

Type ```Anaconda Navigator``` in you start menu search box (in Windows) and press enter to open the Anaconda Navigator. You will see something like: ![this](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Anaconda%20Navigator.png) and click on Jupyter Notebook to Launch it. 

This will open the localhost in your browser and you will see: ![this](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Localhost.png) click on ```New``` Dropdown arrow on the top-right side and then click on ```Python [conda env.base]*```. This will open the New Jupyter Notebook page like: ![this](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Jupyter%20Notebook.png)

On the right hand side of the Jupyter Notebook you will see Anaconda Assistant where you can chat to get help on your code or if there is any error due to code fault. You will write code in the cell where I typed ```print('hello world')``` and run. There are a few nice keyboard shortcuts to run code and add/delete/move cells in the Jupyter Notebook. 


# **Jupyter Notebook shortcuts**
(for Windows only, Google to see what shortcuts are required for Mac/Linux systems)

-- Ctrl + Shift + Enter run the current cell, select below

-- Alt + Enter run the current cell, insert below

-- Ctrl + S save and checkpoint


**To exit the code/edit mode, press ```Esc``` from you keyboard (located on the top left of your keyboard).** Once the ```Esc``` is pressed the cell will enter into command mode. 

## **The following shortcuts are handy in Command mode:** 

-- Enter take you into edit mode

-- H show all shortcuts

-- Up select cell above

-- Down select cell below

-- Shift + Up extend selected cells above

-- Shift + Down extend selected cells below

-- A insert cell above

-- B insert cell below

-- X cut selected cells

-- C copy selected cells

-- V paste cells below

-- Shift + V paste cells above

-- D, D (press the key twice) delete selected cells

-- Z undo cell deletion

-- S Save and Checkpoint

-- Y change the cell type to Code

-- M change the cell type to Markdown


## **While in edit mode (press ```Enter``` to activate)**

-- Esc take you into command mode

-- Tab code completion or indent

-- Shift + Tab tooltip

-- Ctrl + ] indent

-- Ctrl + [ dedent

-- Ctrl + A select all

-- Ctrl + Z undo

-- Ctrl + Shift + Z or Ctrl + Y redo

-- Ctrl + Home go to cell start

-- Ctrl + End go to cell end

-- Ctrl + Left go one word left

-- Ctrl + Right go one word right



-- Ctrl + Shift + P open the command palette

-- Down move cursor down

-- Up move cursor up


**Play with these shortcuts to see which shortcut you want to use more often. If you are a beginner, it is recommended to type your code instead of copy/paste.** 


# **A nice alternative to Jupyter Notebook is Google/Colab which is truly online and gives the opportunity of using dedicated GPU to run Deep Learning models.**

**Steps:** 
1. You need to have a Google/gmail account
2. type: https://colab.research.google.com/ in the address bar of your browser. You will see: ![this](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Colab.png) Click on ```+ New Notebook```
   
3. Once clicked on ```+ New Notebook``` will open a notebook similar to Jupyter Notebook where we can type and run code: ![this](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/Colab%20Notebook.png)

4. If you need a dedicated free GPU to run your model, click on ```Edit``` from the top menu of the Colab Notebook, then click on ```Notebook Settings```  then click on available GPUs (such as T4 GPU or v5e-1 TPU) and save. ![colabgpu](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/Images/colab%20notebook%20gpu.png)
