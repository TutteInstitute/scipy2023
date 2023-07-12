![](https://github.com/TutteInstitute/.github/raw/main/profile/images/tutte-long.png)

# *Commonplace* detection in categorical telemetry data

[Benoit Hamelin](mailto:benoit.hamelin@cyber.gc.ca) and John Healy<br>
SciPy 2023

This repository is offered as a complement to [this poster](https://drive.google.com/file/d/1ZijF656jj7x8AobIypdyQErn0hXOpIFU/view?usp=sharing).

## Poster summary

Cyber defense operations today are difficult, tedious and expensive tasks.
Cyber threat detection involves running very large amounts of monitoring telemetry through heuristics and analytics that, while sensitive to the activity of adversaries, tends to be poorly specific &mdash; false positive rates seldom break below 95%.
Automating threat detection eludes the industry because data that characterizes intrusions and offensive tactics is sparse, rare and thus goes unlabeled.

As things stand, most of the monitoring telemetry that is captured and stored describes normal computations going on within IT infrastructures.
It thus seems reasonable to attempt to label and characterize the hallmarks of *commonplace* processes:
computations that occur often and that generate regular event patterns.
These commonplace events constitute *noise* with respect to the work of detecting malicious activity,
so we posit that taking it away from the investigative focus of cyber analysts stand to help them complete such investigations with improved reliability and efficiency, and at a lower cost.

We propose in this work a data representation that enables interactive visualization of the computations that make up a [dataset](https://github.com/FiveDirections/OpTC-data) of *host-based* telemetry, as well as a flexible toolkit for building a dashboard that enables the labeling of commonplace processes.
We also propose a methodology for detecting the subset of process behaviors that can be construed as commonplace, along with an approach to classify new process instances against this characterization.

## Contents

We present here two notebooks:

1. [Data engineering](01%20Data%20Engineering.ipynb): computes a 2D data representation of processes characterized as *bags of events* where local structure reflects similarity between processes.
1. [Interactive visualization](02%20Interactive%20visualization.ipynb): produces a Panel-based dashboard for visualizing and examining the data representation of the first notebook as a **data map**, and for adding categorical information regarding the commonplaceness of the process instances.

## Usage

### Quick and easy visualization of a canned data representation in Binder

Click this: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tutteinstitute/scipy2023/HEAD?labpath=02%20Interactive%20visualization.ipynb)

The setup takes 15-20 minutes.
Once the notebook is open, select the **Run** menu, and click **Run all**.
Zip to the end of the notebook while some nuts get crunched:
within a minute, you will be enjoying the visualization tool.

### In-depth reproduction of calculations and running visualization *in situ*

Put together the environment in which the notebooks were authored:

```sh
conda env create
conda activate commonplace-detection-optc
python -m ipykernel install --user --name commonplace-detection-optc --display-name 'Commonplace detection in categorical telemetry data'
```

This last command will set up a kernel that can be either used the same way either by starting Jupyter Lab from the same shell, or through an ad hoc Jupyterhub/Lab instance.
