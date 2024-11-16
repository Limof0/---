def playing_field(field): # Показывает игровое поле
    print("  0  1  2")
    for i in range(3):
        row = f"{i} "
        for j in range(3):
            row += field[i][j] + " "
        print(row)

def game(): # Функция для начала игры
    gaming = [['-' for _ in range(3)] for _ in range(3)]
    current_player = 'X'

    while True:
        playing_field(gaming)
        x, y = map(int, input(f"Игрок {current_player}, введите координаты (x y): ").split())

        if сorrect_coordinates(gaming, x, y):
            gaming[x][y] = current_player
            winner = check_winner(gaming)
            if winner:
                playing_field(gaming)
                print(f"Победитель: {winner}")
                break
            current_player = '0' if current_player == 'X' else 'X'
        else:
            print("Некорректный ход, попробуйте снова.")

def check_winner(examination): # Проверка на наличие победителя или ничьи
    for i in range(3):
        if examination[0][i] == examination[1][i] == examination[2][i] != '-':
            return examination[0][i]
        if examination[i][0] == examination[i][1] == examination[i][2] != '-':
            return examination[i][0]
    if examination[0][0] == examination[1][1] == examination[2][2] != '-':
        return examination[0][0]
    if examination[0][2] == examination[1][1] == examination[2][0] != '-':
        return examination[0][2]
    if all(cell != '-' for row in examination for cell in row):
        return 'Дружба'
    return None

def сorrect_coordinates(position, x, y): # Проверяет были ли правильно введены координаты (x y)
    return 0 <= x < 3 and 0 <= y < 3 and position[x][y] == '-'

if __name__ == "__main__":
    game()
