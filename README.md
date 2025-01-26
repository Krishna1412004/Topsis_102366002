TOPSIS Methodology Implementation
This project implements the TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) method to evaluate and rank alternatives based on multiple criteria. The program reads input data, processes it according to the TOPSIS algorithm, and outputs the ranked alternatives with their scores.

Table of Contents
Overview
Requirements
Input File Format
How to Run
Error Handling
Example
Output
License
Overview
This program uses the TOPSIS method for decision-making by considering a set of alternatives, each evaluated based on several criteria. The program:

Normalizes the input data.
Applies weights to each criterion.
Calculates the Euclidean distance from the ideal and worst solutions.
Computes the TOPSIS scores.
Ranks the alternatives based on their scores.
Requirements
The following Python libraries are required to run the program:

pandas
numpy
You can install them using pip:

bash
Copy
Edit
pip install pandas numpy
Input File Format
The input file should be a CSV file with the following format:

The first column should contain the names of the alternatives (e.g., Fund Names).
From the second column onwards, the file should contain numerical data representing the criteria for each alternative.
Example Input (102366002_data.csv):
csv
Copy
Edit
Fund Name, P1, P2, P3, P4, P5
M1, 0.84, 0.71, 6.7, 42.1, 12.59
M2, 0.91, 0.83, 7.0, 31.7, 10.11
M3, 0.79, 0.62, 4.8, 46.7, 13.23
M4, 0.78, 0.61, 6.4, 42.4, 12.55
M5, 0.94, 0.88, 3.6, 62.2, 16.91
M6, 0.88, 0.77, 6.5, 51.5, 14.91
M7, 0.66, 0.44, 5.3, 48.9, 13.83
M8, 0.93, 0.86, 3.4, 37.0, 10.55
Notes:
The input file must contain at least three columns: the first column for alternative names and at least two columns for numerical criteria.
The second to last columns should contain only numeric values.
Impacts should be either + or -.
How to Run
Clone or download the repository.
Prepare your input CSV file (input_file.csv).
Run the Python script with the following command:
bash
Copy
Edit
python topsis.py input_file.csv weights impacts result_file.csv
Command-Line Arguments
input_file.csv: The CSV file containing the dataset to be evaluated.
weights: A comma-separated list of weights corresponding to each criterion.
impacts: A comma-separated list of impacts (+ for benefit, - for cost).
result_file.csv: The output file where the ranked results will be saved.
Example:
bash
Copy
Edit
python topsis.py 102366002_data.csv "1,1,1,2,1" "+,+,-,+,+" 102366002_result.csv
This will read the input file 102366002_data.csv, apply the TOPSIS method with the given weights and impacts, and save the results in 102366002_result.csv.

Error Handling
The program includes checks for the following:

File Not Found: If the input file doesn't exist or is incorrectly specified.
Invalid Data Format: Ensures the input file contains numeric data for all columns (except the first column).
Invalid Weights and Impacts: Ensures the number of weights, impacts, and criteria match.
Non-Numeric Values: Ensures that the columns containing numerical data do not contain non-numeric values.
Invalid Impacts: Ensures that all impacts are either + or -.
Example
Sample Output:
For the input:

csv
Copy
Edit
Fund Name, P1, P2, P3, P4, P5
M1, 0.84, 0.71, 6.7, 42.1, 12.59
M2, 0.91, 0.83, 7.0, 31.7, 10.11
M3, 0.79, 0.62, 4.8, 46.7, 13.23
M4, 0.78, 0.61, 6.4, 42.4, 12.55
M5, 0.94, 0.88, 3.6, 62.2, 16.91
M6, 0.88, 0.77, 6.5, 51.5, 14.91
M7, 0.66, 0.44, 5.3, 48.9, 13.83
M8, 0.93, 0.86, 3.4, 37.0, 10.55
The output in the 102366002_result.csv file might look like this:

csv
Copy
Edit
Fund Name, P1, P2, P3, P4, P5, Topsis Score, Rank
M1, 0.84, 0.71, 6.7, 42.1, 12.59, 0.84, 3
M2, 0.91, 0.83, 7.0, 31.7, 10.11, 0.79, 4
M3, 0.79, 0.62, 4.8, 46.7, 13.23, 0.92, 1
M4, 0.78, 0.61, 6.4, 42.4, 12.55, 0.88, 2
M5, 0.94, 0.88, 3.6, 62.2, 16.91, 0.68, 6
M6, 0.88, 0.77, 6.5, 51.5, 14.91, 0.75, 5
M7, 0.66, 0.44, 5.3, 48.9, 13.83, 0.61, 7
M8, 0.93, 0.86, 3.4, 37.0, 10.55, 0.77, 8
License
This project is licensed under the MIT License - see the LICENSE file for details.
