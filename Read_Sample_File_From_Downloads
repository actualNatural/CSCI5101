import os

def read_sudoku_from_file(filename):
    # Get the user's home directory
    home_directory = os.path.expanduser("~")

    # Create the full path to the Downloads directory
    downloads_directory = os.path.join(home_directory, "Downloads")

    # Create the full path to the file
    file_path = os.path.join(downloads_directory, filename)

    # Check if the file exists before attempting to read
    if os.path.exists(file_path):
        with open(file_path, 'r') as file:
            # Read the contents of the file
            file_contents = file.read()
            # Split the contents into rows
            rows = file_contents.strip().split('\n')

            # Convert the string representation to a 2D list (grid)
            grid = [[int(num) if num != '0' else 0 for num in row.split()] for row in rows]

            return grid
    else:
        print(f"The file {filename} does not exist in the Downloads directory.")

# Example usage
filename = "Sample.txt"
sudoku_grid = read_sudoku_from_file(filename)

if sudoku_grid:
    print("Sudoku Grid:")
    for row in sudoku_grid:
        print(row)
