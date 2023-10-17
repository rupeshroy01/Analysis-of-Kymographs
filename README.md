# Kymograph Processing Tool

This repository contains a Python script to process kymographs. This tool was designed to analyze single or multi-channel kymographs and extract vital data from them, including the trajectory of specific points of interest and their corresponding intensities. The software not only identifies these trajectories but also refines them for smoother and more consistent analysis. All these results, along with peak intensities, are then exported to various formats such as PNG images, Excel files, and PowerPoint presentations.

## Features

- **Folder-based Batch Processing:** The script processes all `.tif` kymograph files present in a chosen directory.
- **Trajectory Smoothing:** Advanced algorithm to smooth the trajectory, compensating for variations more than 3 pixels in adjacent pixels.
- **Peak Detection:** Identifies peak intensities and exports them as Excel files.
- **Multi-channel Support:** Handles both grayscale and two-channel kymographs (green and red channels).
- **Visualization:** Generates PNG images displaying the smoothed trajectory overlay on the kymograph, and plots intensity along the trajectory.
- **PowerPoint Summaries:** For each `.tif` file, creates a comprehensive PowerPoint slide with both the trajectory overlay and intensity plot.

## Usage

1. Run the script.
2. A dialog will appear asking you to select the folder containing the `.tif` kymograph files.
3. The script will then process each file, exporting results to relevant sub-folders.

## Dependencies

- numpy
- tifffile
- matplotlib
- pandas
- tkinter
- pptx
- scipy

# Analysis-of-Kymographs

**Part 2 in the next cell**
Peak Analysis Tool

This script enables users to process data files in a specified directory, specifically analyzing and visualizing the average peak intensities from .xlsx files. It makes use of the find_peaks function from the scipy.signal module to identify and mark the peaks in intensity profiles.

Features:
Allows users to select the directory containing analysis files using a GUI dialog.
Automatically detects and differentiates between 'green' and 'red' data from filenames.
Generates bar plots showcasing the average peak values for both green and red data.
Saves these plots to an auto-generated "plots" directory.
Creates an Excel file containing average peak data.
For each intensity profile, the tool creates a visualization with identified peaks marked using red hollow circles.
Usage:
Simply run the script and use the GUI dialog to select the directory containing your analysis files. The script will handle the rest, processing each .xlsx file and generating the necessary visualizations and summaries.

**Part 3 in the next cell**
Kymograph Data Splitter: I have split the trajectory data from red and green to make it easy for Mean Squared Displacement analyses. 

This script provides a solution for users who have a folder with an Excel file (all_trajectories.xlsx) containing multiple sheets of kymograph data. The sheets within this file represent either "green" or "red" trajectories. The objective of the script is to read this master Excel file, filter the trajectories based on their color designation (green or red), and save them into two separate Excel files.

Features:
GUI Directory Picker: The script initiates a GUI-based directory picker using the tkinter library, allowing users to easily select the folder containing the master Excel file.
Trajectory Extraction: It reads the master Excel file sheet by sheet. If a sheet's name ends with "green", its data is considered a green trajectory. Conversely, if a sheet's name ends with "red", its data is deemed a red trajectory.
File Output: The filtered green and red trajectories are saved into two separate Excel files (green_all_trajectories.xlsx and red_all_trajectories.xlsx), retaining the original sheet names.
Usage:
To use the script:

Ensure you have the pandas, xlsxwriter, and tkinter libraries installed.
Run the script.
When prompted, select the folder containing the all_trajectories.xlsx file using the GUI directory picker.
Once executed, the script will create two new Excel files in the same directory, segregating the green and red trajectories.
Code Overview:
Initialization: The script initializes the required libraries and sets up the GUI directory picker to obtain the target folder path.
Data Reading: It reads the master Excel file (all_trajectories.xlsx) and iterates through its sheets.
Trajectory Filtering: For each sheet, based on the suffix of the sheet name ("green" or "red"), the data is segregated into separate trajectory dictionaries.
Output Generation: Two separate Excel files are generated for green and red trajectories, with the original sheet names retained.
This should provide a clear overview for anyone who intends to use or understand your script.

**Part 4**

The code contains a combined function to export both average and maximum peak intensities.  
Author

Developed by me, with all the scripting from ChatGPT.
