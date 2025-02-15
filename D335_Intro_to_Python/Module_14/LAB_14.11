# Step 1: Prompt user for the file name
filename = input("Enter the filename: ")

# Step 2: Open the file and read its contents
try:
    with open(filename, 'r') as file:
        lines = file.readlines()  # Read all lines into a list

    # Step 3: Check if the file is empty
    if not lines:
        exit()  # No output if the file is empty

    # Step 4: Process each line in the file
    for line in lines:
        filename = line.strip()  # Remove any extra spaces/newlines
        new_filename = filename.replace("_photo.jpg", "_info.txt")  # Modify the filename
        print(new_filename)  # Print the modified filename

except FileNotFoundError:
    print(f"Error: The file '{filename}' was not found.")