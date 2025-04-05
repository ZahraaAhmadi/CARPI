# CARPI Process Map Generator

This Python notebook application provides an interactive interface for generating Directly-Follows Graphs (DFG) from event logs using PM4Py. 

An interactive Jupyter notebook tool for generating process maps from event logs using [PM4Py](https://pm4py.fit.fraunhofer.de/).  
Inspired by **Disco**, this tool allows users to control activity specialization and filter out low-frequency paths using an intuitive slider-based interface.

---

## Features

- Load CSV event logs
- Select activity specialization level (General → Level1 → Level2)
- Filter most frequent paths using a Disco-style **Top % Paths** slider
- Visualize Directly-Follows Graphs (DFGs) using PM4Py
- Interactive UI with `ipywidgets`

---

## Interface Overview

- **Activity Level Sliders**: Choose detail level for each activity.
- **Top % Paths Slider**: Dynamically filter out infrequent paths.
- **Generate Process Map**: Render the process model with PM4Py.

---

## Input Format

The input log file must be a CSV with the following columns:

| Column Name                   | Description                               |
|------------------------------|-------------------------------------------|
| `case_id`                    | Unique identifier for each process instance |
| `activity`                   | Name of the activity                       |
| `timestamp`                  | Timestamp of the event                    |
| `activityname-Level1` | Optional activity specialization field     |
| `activityname-Level2` | Optional deeper specialization field       |

---

## Key Components

- **Python 3**
- **Jupyter Notebook**
- [Pandas](https://pandas.pydata.org/)
- [ipywidgets](https://ipywidgets.readthedocs.io/)
- [PM4Py](https://pm4py.fit.fraunhofer.de/)
- Pandas: Used for loading and manipulating the event log.
- IPyWidgets: Used to build the interactive user interface (sliders, buttons, layout).
- PM4Py:
  - dfg_factory: Extracts the Directly-Follows Graph (DFG) from the event log.
  - g_vis: Visualizes the DFG with frequency annotations.
  - log_converter: Converts Pandas DataFrame into PM4Py event log format.
  - start_activities_get / end_activities_get: Used to determine start and end points for proper DFG rendering.



