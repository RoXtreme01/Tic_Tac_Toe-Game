# Tic_Tac_Toe-Game
Hello friends, this is a Simple Tutorial Program for Python Tkinter Beginners, In advance version You can Also Create it better than me using Images.

# Only For PC Screen 
# Don't contais any Image

# Step 1 : Open your cmd and type " pip install tkinter "
# Step 2 : Run this program 

import tkinter as tk
from tkinter import messagebox

# Initialize the main window
root = tk.Tk()
root.geometry("600x600")  # Set window size
root.title("Tic Tac Toe")  # Set window title
root.configure(bg="black")  # Set background color
root.resizable(False, False)  # Disable window resizing

# Create a frame to hold the game buttons
frame = tk.Frame(root, bg="#303030", width=500, height=500).pack(pady=10)

# Initialize a variable to track the turn, where odd numbers represent Player X and even numbers represent Player O
roundx = 1

# Function to check the win condition after each move
def win_condition():
    # Check all possible winning combinations
    if (button1.cget("text") == button2.cget("text") == button3.cget("text") != "" or
        button4.cget("text") == button5.cget("text") == button6.cget("text") != "" or
        button7.cget("text") == button8.cget("text") == button9.cget("text") != "" or
        button1.cget("text") == button4.cget("text") == button7.cget("text") != "" or
        button2.cget("text") == button5.cget("text") == button8.cget("text") != "" or
        button3.cget("text") == button6.cget("text") == button9.cget("text") != "" or
        button1.cget("text") == button5.cget("text") == button9.cget("text") != "" or
        button3.cget("text") == button5.cget("text") == button7.cget("text") != ""):
        # Show the winner in a message box
        messagebox.showinfo("Tic Tac Toe", f"Player {button1.cget('text')} wins!")
        restart()  # Restart the game after a win

# Function to handle button clicks (player's move)
def Input(val):
    global roundx  # Reference the global roundx variable

    # Determine which button was clicked and update it with "X" or "O" based on the current round
    if val == "a" and button1.cget("text") == "":
        button1.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "b" and button2.cget("text") == "":
        button2.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "c" and button3.cget("text") == "":
        button3.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "d" and button4.cget("text") == "":
        button4.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "e" and button5.cget("text") == "":
        button5.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "f" and button6.cget("text") == "":
        button6.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "g" and button7.cget("text") == "":
        button7.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "h" and button8.cget("text") == "":
        button8.configure(text="X" if roundx % 2 != 0 else "O")
    elif val == "i" and button9.cget("text") == "":
        button9.configure(text="X" if roundx % 2 != 0 else "O")

    win_condition()  # Check if the move resulted in a win
    roundx += 1  # Increment the round number

# Function to reset the game board
def restart():
    global roundx  # Reference the global roundx variable
    roundx = 1  # Reset the round counter
    # Clear the text on all buttons
    button1.configure(text="")
    button2.configure(text="")
    button3.configure(text="")
    button4.configure(text="")
    button5.configure(text="")
    button6.configure(text="")
    button7.configure(text="")
    button8.configure(text="")
    button9.configure(text="")

# Create buttons for each cell in the Tic Tac Toe grid
button1 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("a"))
button1.place(x=64, y=30)

button2 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("b"))
button2.place(x=224, y=30)

button3 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("c"))
button3.place(x=384, y=30)

button4 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("d"))
button4.place(x=64, y=185)

button5 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("e"))
button5.place(x=224, y=185)

button6 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("f"))
button6.place(x=384, y=185)

button7 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("g"))
button7.place(x=64, y=340)

button8 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("h"))
button8.place(x=224, y=340)

button9 = tk.Button(frame, text="", height=3, width=7, font="Arial 25 bold", bg="white", fg="black", command=lambda: Input("i"))
button9.place(x=384, y=340)

# Create a "Restart" button to reset the game
restart = tk.Button(root, text="Restart", width=47, height=1, bg="Blue", fg="white", font="Arial 15 bold", relief="raised", command=restart)
restart.place(x=10, y=550)

# Start the Tkinter main loop
root.mainloop()
