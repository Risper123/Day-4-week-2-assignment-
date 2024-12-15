I'm# Day-4-week-2-assignment-
Assignment for week 2 day 4
File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
# Import necessary modules
import os

# Function to read and modify file content
def read_and_modify_file(input_filename, output_filename):
    try:
        with open(input_filename, 'r') as infile:
            content = infile.read()  # Read the file content
            modified_content = content.upper()  # Example modification: converting to uppercase

        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)  # Write the modified content to a new file
            
        print(f"File has been successfully modified and saved as '{output_filename}'")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' does not exist.")
    except IOError as e:
        print(f"Error: An error occurred while reading or writing to the file: {e}")

# Ask the user for the input filename
input_filename = input("Enter the name of the file you want to read: ")

# Check if the file exists and is readable
if os.path.exists(input_filename) and os.access(input_filename, os.R_OK):
    # Proceed with reading and modifying the file
    output_filename = input("Enter the name of the output file: ")
    read_and_modify_file(input_filename, output_filename)
else:
    print(f"Error: The file '{input_filename}' either does not exist or cannot be read.")
    
