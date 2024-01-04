# this is a little program to check the winning rate when playing Game-Rock-Paper-Scissors via a personalize rule
import random

repeat_times = int(input("Please input the repeat count："))
def allocate_points():
    while True:
        points = random.sample(range(0, 6), 3)
        if sum(points) == 8:
            return points

# assign point to A1, B1 and C1
A1, B1, C1 = allocate_points()

def play_game():
    win_count = 0
    win_combinations = {}  # to storage the won combo of Player1 and what its combo like

    for _ in range(repeat_times):
        # initiate the score and init value
        score_a = 8
        score_b = 8
        values_a = [0, 0, 0]
        values_b = [0, 0, 0]

        # assign the init value
        values_a = allocate_points()
        values_b = allocate_points()

        # Judge whether Player1 and Player2 reach the standard
        if values_a[0] >= values_b[1]:
            score_b -= min(values_b[1], 2)
        if values_a[1] >= values_b[2]:
            score_b -= min(values_b[2], 2)
        if values_a[2] >= values_b[0]:
            score_b -= min(values_b[0], 2)
        if values_a[0] <= values_b[2]:
            score_a -= min(values_a[0], 2)
        if values_a[1] <= values_b[0]:
            score_a -= min(values_a[1], 2)
        if values_a[2] <= values_b[1]:
            score_a -= min(values_a[2], 2)

        # Judge which score is higher between Player1 and Player2
        if score_a > score_b:
            win_count += 1
            combination = tuple(values_a)
            if combination in win_combinations:
                win_combinations[combination] += 1
            else:
                win_combinations[combination] = 1

    # Output the combination with most won times of Player1
    print("Plaer1 wons:", win_count)
    if win_count > 0:
        max_combination = max(win_combinations, key=win_combinations.get)
        print("The combination with most won times:", max_combination)

# Run the game
play_game()
