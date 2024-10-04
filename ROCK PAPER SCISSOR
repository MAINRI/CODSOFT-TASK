import tkinter as tk
import random


def play_round(user_choice):
    computer_choice = random.choice(choices)
    winner = determine_winner(user_choice, computer_choice)

    result_label.grid(row=3, columnspan=3, pady=10)

    if winner == "Tie":
        result_var.set("It's a tie!")
    else:
        result_var.set(f"{winner} wins!")

    if winner == "User":
        user_score_var.set(user_score_var.get() + 1)
    elif winner == "Computer":
        computer_score_var.set(computer_score_var.get() + 1)


def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "Tie"
    elif (
        (user_choice == "Rock" and computer_choice == "Scissors")
        or (user_choice == "Scissors" and computer_choice == "Paper")
        or (user_choice == "Paper" and computer_choice == "Rock")
    ):
        return "User"
    else:
        return "Computer"


def play_again():
    result_var.set("")
    result_label.grid_forget()
    user_score_var.set(0)
    computer_score_var.set(0)


choices = ["Rock", "Paper", "Scissors"]

root = tk.Tk()
root.title("Rock-Paper-Scissors Game")

result_var = tk.StringVar()
user_score_var = tk.IntVar()
computer_score_var = tk.IntVar()

frame = tk.Frame(root)
frame.pack(padx=10, pady=10)

tk.Label(frame, text="Rock Paper Scissors", font="normal 20 bold", fg="green").grid(row=0, column=0, columnspan=3, pady=5)

user_label = tk.Label(frame, text="User", font='10').grid(row=1, column=0, padx=10, pady=10)
vs_label = tk.Label(frame, text="VS", font="normal 10 bold").grid(row=1, column=1, padx=10, pady=10)
computer_label = tk.Label(frame, text="Computer", font='10').grid(row=1, column=2, padx=10, pady=10)

result_label = tk.Label(frame, textvariable=result_var, font="normal 20 bold", bg="white", width=15, borderwidth=2, relief="solid")

tk.Button(frame, text="Rock", font='10', width=7, command=lambda: play_round("Rock")).grid(row=5, column=0, padx=10, pady=10)
tk.Button(frame, text="Paper", font='10', width=7, command=lambda: play_round("Paper")).grid(row=5, column=1, padx=10, pady=10)
tk.Button(frame, text="Scissors", font='10', width=7, command=lambda: play_round("Scissors")).grid(row=5, column=2, padx=10, pady=10)

tk.Button(frame, text="Play Again", font='10',fg="white", bg="black", command=play_again).grid(row=6, columnspan=3, pady=10)

tk.Label(frame, textvariable=user_score_var, font='10').grid(row=2, column=0, padx=10, pady=5)
tk.Label(frame, textvariable=computer_score_var, font='10').grid(row=2, column=2, padx=10, pady=5)

root.mainloop()
