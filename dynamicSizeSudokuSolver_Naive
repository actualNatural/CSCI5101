def printing(arr):
    for i in range(len(arr)):
        for j in range(len(arr[i])):
            print(arr[i][j], end=" ")
        print()

def isSafe(grid, row, col, num):
    # Check if 'num' is not in the current row
    for x in range(len(grid[0])):
        if grid[row][x] == num:
            return False

    # Check if 'num' is not in the current column
    for x in range(len(grid)):
        if grid[x][col] == num:
            return False

    return True

def solveSudoku(grid, row, col):
    if row == len(grid) - 1 and col == len(grid[0]):
        return True

    if col == len(grid[0]):
        row += 1
        col = 0

    if grid[row][col] > 0:
        return solveSudoku(grid, row, col + 1)

    for num in range(1, max(len(grid), len(grid[0])) + 1, 1):
        if isSafe(grid, row, col, num):
            grid[row][col] = num
            if solveSudoku(grid, row, col + 1):
                return True
            grid[row][col] = 0

    return False

# Driver Code
#grid = [
#    [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
#]

grid = [
    [1, 0, 3, 0, 0, 6, 0, 8, 0, 10]
]

if solveSudoku(grid, 0, 0):
    printing(grid)
else:
    print("No solution exists")
