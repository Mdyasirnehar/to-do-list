# to-do-list

import tkinter as tk
from tkinter import messagebox

# Function to add a task
def add_task():
    task = entry.get()
    if task != "":
        listbox.insert(tk.END, task)
        entry.delete(0, tk.END)
    else:
        messagebox.showwarning("Warning", "You must enter a task.")

# Function to delete a selected task
def delete_task():
    try:
        selected_task_index = listbox.curselection()[0]
        listbox.delete(selected_task_index)
    except:
        messagebox.showwarning("Warning", "You must select a task to delete.")

# Create the main window
root = tk.Tk()
root.title("To-Do List")

# Create an entry field
entry = tk.Entry(root, width=40)
entry.pack(pady=10)

# Create an "Add Task" button
add_button = tk.Button(root, text="Add Task", command=add_task)
add_button.pack(pady=5)

# Create a listbox to show tasks
listbox = tk.Listbox(root, width=50, height=10)
listbox.pack(pady=10)

# Create a "Delete Task" button
delete_button = tk.Button(root, text="Delete Selected Task", command=delete_task)
delete_button.pack(pady=5)

# Run the application
root.mainloop()
