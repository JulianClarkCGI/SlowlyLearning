sub = []
sub.append([3, 0, 6, 5, 0, 8, 4, 0, 0])
sub.append([5, 2, 0, 0, 0, 0, 0, 0, 0])
sub.append([0, 8, 7, 0, 0, 0, 0, 3, 1])
sub.append([0, 0, 3, 0, 1, 0, 0, 8, 0])
sub.append([9, 0, 0, 8, 6, 3, 0, 0, 5])
sub.append([0, 5, 0, 0, 9, 0, 6, 0, 0])
sub.append([1, 3, 0, 0, 0, 0, 2, 5, 0])
sub.append([0, 0, 0, 0, 0, 0, 0, 7, 4])
sub.append([0, 0, 5, 2, 0, 6, 3, 0, 0])


def solve(su):
    find = find_empty(su)
    if not find:
        return True
    else:
        row, col = find

    for i in range(1, 10):
        if valid(su, i, (row, col)):
            su[row][col] = i

            if solve(su):
                return True

            su[row][col] = 0

    return False


def valid(su, num, pos):
    for i in range(len(su[0])):
        if su[pos[0]][i] == num and pos[1] != i:
            return False

    for i in range(len(su)):
        if su[i][pos[1]] == num and pos[0] != i:
            return False

    box_x = pos[1] // 3
    box_y = pos[0] // 3

    for i in range(box_y * 3, box_y * 3 + 3):
        for j in range(box_x * 3, box_x * 3 + 3):
            if su[i][j] == num and (i, j) != pos:
                return False

    return True


def print_sub(su):
    for i in range(len(su)):
        if i % 3 == 0 and i != 0:
            print("------------------------")

        for j in range(len(su[0])):
            if j % 3 == 0 and j != 0:
                print(" | ", end="")

            if j == 8:
                print(su[i][j])
            else:
                print(str(su[i][j]) + " ", end="")


def find_empty(su):
    for i in range(len(su)):
        for j in range(len(su[0])):
            if su[i][j] == 0:
                return (i, j)

    return None


print_sub(sub)
print("")
print("Starting To Find Optimal Solution!")
print("")

solve(sub)

print("Optimal Solution Found!")
print("")
print_sub(sub)
