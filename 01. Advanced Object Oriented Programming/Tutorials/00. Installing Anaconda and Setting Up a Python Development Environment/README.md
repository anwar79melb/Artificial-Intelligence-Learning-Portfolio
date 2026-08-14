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

Type ```Anaconda Navigator``` in you start menu search box (in Windows) and press enter to open the Anaconda Navigator. You will see something like ![this](https://github.com/anwar79melb/Artificial-Intelligence-Learning-Portfolio/blob/main/01.%20Advanced%20Object%20Oriented%20Programming/images/image.png) and click on Jupyter Notebook to Launch it. 


