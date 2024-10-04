import tkinter as tk
from tkinter import messagebox

# Function to add a new task to the to-do list
def add_task():
    task = entry.get()
    if task:
        listbox.insert(tk.END, task)
        entry.delete(0, tk.END)
    else:
        messagebox.showwarning("Warning", "Please enter a task.")

# Function to delete a selected task from the to-do list
def delete_task():
    try:
        index = listbox.curselection()
        listbox.delete(index)
    except:
        messagebox.showwarning("Warning", "Please select a task to delete.")

# Function to update/edit the selected task
def update_task():
    try:
        index = listbox.curselection()
        updated_task = entry.get()
        if updated_task:
            listbox.delete(index)
            listbox.insert(index, updated_task)
            entry.delete(0, tk.END)
        else:
            messagebox.showwarning("Warning", "Please enter an updated task.")
    except:
        messagebox.showwarning("Warning", "Please select a task to update.")

# Function to mark the selected task as done
def mark_as_done():
    try:
        index = listbox.curselection()
        task = listbox.get(index)
        updated_task = task + " (Done)"
        listbox.delete(index)
        listbox.insert(index, updated_task)
    except:
        messagebox.showwarning("Warning", "Please select a task to mark as done.")

# Create the main window
window = tk.Tk()
window.title("To-Do List")


# Create the to-do list
listbox = tk.Listbox(window, width=50, height=10, font=("Arial", 12))
listbox.pack(pady=20)

# Create the scrollbar
scrollbar = tk.Scrollbar(window)
scrollbar.pack(side=tk.RIGHT, fill=tk.Y)

# Add the scrollbar to the to-do list
listbox.config(yscrollcommand=scrollbar.set)
scrollbar.config(command=listbox.yview)

# Create the task entry field
entry = tk.Entry(window, font=("Arial", 12))
entry.pack(pady=20)

# Create buttons to add, delete, update, and mark as done tasks
add_button = tk.Button(window, text="Add Task", command=add_task)
add_button.pack(pady=10)
delete_button = tk.Button(window, text="Delete Task", command=delete_task)
delete_button.pack(pady=10)
update_button = tk.Button(window, text="Update Task", command=update_task)
update_button.pack(pady=10)
mark_done_button = tk.Button(window, text="Mark as Done", command=mark_as_done)
mark_done_button.pack(pady=10)

# Start the GUI main loop
window.mainloop()
