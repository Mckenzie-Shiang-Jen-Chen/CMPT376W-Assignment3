# LogLens

LogLens is a command-line Python script for counting records in a CSV log file. 

This guide is for computing students and new technical interns who have knowledge about CSV files and used a terminal, but have not used LogLens before. For the detailed setup guide, please look at the installation guide. 

## What LogLens do
* Read a CSV log file and print the number of records that match a log level or the total number of records.
* Runs locally on your computer. It does not transmit, upload, or store your data outside your computer.
* It reads but does not repair, rewrite, or otherwise modify the input CSV.
* it does not diagnose system failures; it count records by log level. 

## Requirements 
* Python 3.10 or newer.
* LogLens uses only the Python standard library, pip install is not required.

Note: This guide use python command, however some computer the Python launcher is python3 or py instead. If python command doesn't work, try one of these instead.

## Get started
1. Get the LogLens files from the repository guide. The installation guide will explain the process.
2. Open a terminal in the repository root, which is the folder that contains `loglens.py`. Run all LogLens commands from this folder.
3. Run the LogLens on the sample log and use `--level ERROR` to count its `ERROR` records. 

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```
Expected output:
```text
Records matching ERROR: 2
```
LogLens work as intended if the output is like the one above. 

## Using the program
Note: `--file` is required for the CSV file to read.

Count all records in the sample by omitting `--level`:
```bash
python loglens.py --file data/sample_logs.csv
```
Expected output:
```text
Records matching ALL: 6
```

Show the valid command-line options:
```bash
python loglens.py --help
```
Note: To count the records in your own file, change the `data/sample_file.csv` into your CSV file choice and location of where the file is.

## Input format

LogLens expected the CSV column headers named exactly `timestamp`, `level`, `message `.
The `level ` argument that is accepted are `INFO`, `WARN `, and `ERROR` in uppercase. 

## Getting help and report problems
If a command does not work:
1. Check the troubleshooting section in installation guide
2. Run `python loglens.py --help` to check the valid command-line.

Report the problem to the repository developers, describe what problem you ran into, what is the error message. 

Note: it is important not to upload any file that contains private/sensitive logs publicly. 

