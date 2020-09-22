---
layout: post
title: Production batch processing
date:   2020-09-22
categories: engineering-management
---

### What is batch processing?
Batch processing is the processing of a large volume of data at the same time. Data is collected over a period of time, and then processed all at once. Batch data processing can be contrasted with real-time data processing, where data is processed as it is collected.

Most data processing jobs in the data warehouse are batch processing jobs. Unless you are working with streaming data, chances are, a large batch of data is loaded into your data warehouse for further processing. Computation resources can be optimized for batch processing jobs, for example, Spark parellelizes your code to run on large batches of data.

Most AI and ML algorithms also work with large batches of data. By nature, machine learning models are only effective when they are used with large datasets. One batch of data is used to train the model, another batch of data is used to test the model, and finally, the model is used to evaluate another batch of data.

This style guide introduces a framework for structuring production batch data processing jobs. We tried to keep the framework general so it would remain relevant for different programming languages.

# **The Framework**
Most of us have encountered encountered coding projects which were difficult to understand. We all start out as beginners, so it is likely that most of us have also created messy coding projects. Consider the following file structure.

```
.
├── BDJ - Notebook.ipynb
├── KRJ - Notebook.ipynb
├── testing.py
├── dataset_1.csv
├── dataset_2.csv
├── execute_algorithm.py
```

The most immediate question when presented with the file structure above is, how do I execute this code?

### 1. Single Point of Execution
Think of each batch processing job as it's own program. The program must have a single point of execution. There must be a single file which executes the entire batch processing job. For example, you could have a file `run.py` which executes the entire pipeline. Executing the job should be as simple as entering a command in the command line.
```
python run.py
```

### 2. Isolated Environment
A program should be capable of being run on different machines. Ideally, your program will be easy to execute on your local machine, a server, and your colleagues' computers. Every computer usually has different packages installed, which can lead to dependency conflicts. Each project should have an isolated execution environment, which is created by an `install.bat` file.

### 3. Self-Contained Documentation
Documentation should be self-contained with the code. Every user who clones the repository should also have the documentation on their machine. This avoids any situations when someone is trying to use the code but cannot access the documentation. The project overview should be specified in `README.md` at the root of the repository. When possible, the project should include a *directed acyclic graph*.

### 4. Execution Status
Each step in the project should be evaluated as PASS/FAIL. Either the step was successful, or it wasn't. The program should save the execution status results for user feedback.

### 5. Execution Benchmarking
Each step should also be benchmarked. We measure the execution time of each step in the pipeline, and save the results for user feedback. By measuring execution time, we can identify the steps which are taking the most time to execute, and therefore merit the most focus. We can use the information to further improve execution time of the module.

### 6. Tests
Every program should have tests which are executed at the end of the batch processing job. The tests validate the integrity of the results. At the most basic level, the tests can evaluate whether all the output tables are populated. The more specific you can make your tests, the better. **After fixing a bug, add a complementary test so that the bug is automatically caught if it reappears in the future.**

### 7. User Feedback
The program should provide feedback to the user after execution is finished. Feedback should include:
* overall execution status
* execution status of each step
* execution time of each step
* test results

This list is by no means exhaustive. The more you can standardize the formula for writing batch processing jobs, the easier it will be to deploy ETL and ML solutions. Spend less time worrying about formatting, and more time being creative!

Taking into account the above framework, most of our programs resemble the file structure below.

```
.
├── developement
|	├── Exploratory-Notebooks.ipynb
├── logs
|	├── execution_logs.csv
├── src
|	├── __init__.py
|	├── module.py
├── tests
|	├── test.py
├── 01 Step 1.py
├── 02 Step 2.py
├── 03 Step 3.py
├── install.bat
├── run.py
├── README.md
```