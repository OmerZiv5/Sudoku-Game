board = [[7, 8, 0, 4, 0, 0, 1, 2, 0],
         [6, 0, 0, 0, 7, 5, 0, 0, 9],
         [0, 0, 0, 6, 0, 1, 0, 7, 8],
         [0, 0, 7, 0, 4, 0, 2, 6, 0],
         [0, 0, 1, 0, 5, 0, 9, 3, 0],
         [9, 0, 4, 0, 6, 0, 0, 0, 5],
         [0, 7, 0, 3, 0, 0, 0, 1, 2],
         [1, 2, 0, 0, 0, 7, 4, 0, 0],
         [0, 4, 9, 2, 0, 6, 0, 0, 7]]


def print_board(brd):
    for i in range(9):
        for j in range(9):
            print(brd[i][j], end="")
            if (j == 2) or (j == 5):
                print("|", end="")
            if j == 8:
                print("\n")

        if (i == 2) or (i == 5):
            for k in range(10):
                print("-", end="")
            print("-")


def find_empty(brd):
    for i in range(9):
        for j in range(9):
            if brd[i][j] == 0:
                return i, j
    return None


def valid(pos, num, brd):
    for i in range(9):
        if brd[pos[0]][i] == num and i != pos[1]:
            return False
    for j in range(9):
        if brd[j][pos[1]] == num and j != pos[0]:
            return False
    box_y = pos[0] // 3
    box_x = pos[1] // 3
    for i in range(3 * box_y, 3 * box_y + 3):
        for j in range(3 * box_x, 3 * box_x + 3):
            if brd[i][j] == num and pos != (i, j):
                return False
    return True


def solve(brd):
    find = find_empty(brd)
    if not find:
        return True

    else:
        row, col = find

    for i in range(1, 10):
        if valid((row, col), i, brd):
            brd[row][col] = i
            if solve(brd):
                return True
            brd[row][col] = 0

    return False


solve(board)
print_board(board)
