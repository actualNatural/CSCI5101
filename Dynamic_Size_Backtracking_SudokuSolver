def print_grid(arr):
    for i in range(len(arr)):
        for j in range(len(arr[0])):
            print(arr[i][j], end=" ")
        print()

def find_empty_location(arr, l):
    for row in range(len(arr)):
        for col in range(len(arr[0])):
            if arr[row][col] == 0:
                l[0] = row
                l[1] = col
                return True
    return False

def used_in_row(arr, row, num):
    return num in arr[row]

def used_in_col(arr, col, num):
    return num in [arr[i][col] for i in range(len(arr))]

def used_in_box(arr, row, col, num):
    subgrid_size_row = int(len(arr) ** 0.5)
    subgrid_size_col = int(len(arr[0]) ** 0.5)
    start_row, start_col = subgrid_size_row * (row // subgrid_size_row), subgrid_size_col * (col // subgrid_size_col)
    return num in [arr[i][j] for i in range(start_row, min(start_row + subgrid_size_row, len(arr))) for j in range(start_col, min(start_col + subgrid_size_col, len(arr[0])))]

def check_location_is_safe(arr, row, col, num):
    return not used_in_row(arr, row, num) and not used_in_col(arr, col, num) and not used_in_box(arr, row, col, num)

def solve_sudoku(arr):
    l = [0, 0]

    if not find_empty_location(arr, l):
        return True

    row, col = l[0], l[1]

    for num in range(1, max(len(arr), len(arr[0])) + 1):
        if check_location_is_safe(arr, row, col, num):
            arr[row][col] = num
            if solve_sudoku(arr):
                return True
            arr[row][col] = 0

    return False

# Driver main function to test above functions
if __name__ == "__main__":
    # Creating a 2D array for the grid
    grid = [[0 for x in range(10)]]

    # Assigning values to the grid
    grid[0] = [3, 0, 6, 5, 0, 8, 4, 0, 0, 0]

    # If success print the grid
    if solve_sudoku(grid):
        print_grid(grid)
    else:
        print("No solution exists")
