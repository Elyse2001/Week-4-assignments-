# Week-4-assignments-
File Read &amp; Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file. Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.
def read_and_modify_file():
    try:
        # The user for the filename
        filename = input("Enter the filename to read: ")
        
        # Open the file for reading
        with open(filename, "r") as file:
            content = file.readlines()  # Read all lines
        
        # Modify content (example: add line numbers)
        modified_content = [f"{i+1}: {line}" for i, line in enumerate(content)]
        
        # Create a new file and write modified content
        new_filename = "modified_" + filename
        with open(new_filename, "w") as new_file:
            new_file.writelines(modified_content)
        
        print(f"File successfully modified and saved as {new_filename}")
    
    except FileNotFoundError:
        print("Error: The file does not exist. Please enter a valid filename.")
    except IOError:
        print("Error: Unable to read the file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the function
read_and_modify_file()
