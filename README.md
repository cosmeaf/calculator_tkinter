# Calculator python with tkinter

Python offers several options for developing a GUI (Graphical User Interface). Of all the GUI methods, Tkinter is the most commonly used method. It is a standard Python interface to the Tk GUI toolkit shipped with Python. Python with Tkinter produces the fastest and easiest way to build GUI apps. Creating a GUI using Tkinter is an easy task.

## Starting

These instructions will provide you with a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on deploying the project to an active system.

To create a Tkinter :

```
Importing the module – tkinter
Create the main window (container)
Add any number of widgets to the main window
Apply the Trigger event on the widgets.
Below is what the GUI looks like:
```

### requirements

Import tkinter Package

```
import tkinter as tk
```

### Source Code
```
"""
 Project Calculetor
 Author Cosme Alves
 Date 07/01/2022

 Project Calculator Criated with tkinter
"""

import tkinter as tk

calculation = ""


def add_to_calculation(symbol):
    global calculation
    calculation += str(symbol)
    text_result.delete(1.0, "end")
    text_result.insert(1.0, calculation)


def evaluete_calculation():
    global calculation
    try:
        calculation = str(eval(calculation))
        text_result.delete(1.0, "end")
        text_result.insert(1.0, calculation)

    except:
        clear_filed()
        text_result.insert(1.0, "ERROR")


def clear_filed():
    global calculation
    calculation = ""
    text_result.delete(1.0, "end")


root = tk.Tk()
root.iconbitmap("assets/img/calculator.ico")
root.title("Calculator Python V1.0.0")

text_result = tk.Text(root, height=2, width=16, font=("Arial", 24))
text_result.grid(columnspan=5)

btn_1 = tk.Button(root, text="1", command=lambda: add_to_calculation(1), width=5, font=("Arial", 14))
btn_1.grid(row=2, column=1)
btn_2 = tk.Button(root, text="2", command=lambda: add_to_calculation(2), width=5, font=("Arial", 14))
btn_2.grid(row=2, column=2)
btn_3 = tk.Button(root, text="3", command=lambda: add_to_calculation(3), width=5, font=("Arial", 14))
btn_3.grid(row=2, column=3)
btn_mult = tk.Button(root, text="*", command=lambda: add_to_calculation("*"), width=5, font=("Arial", 14))
btn_mult.grid(row=2, column=4)

btn_4 = tk.Button(root, text="4", command=lambda: add_to_calculation(4), width=5, font=("Arial", 14))
btn_4.grid(row=3, column=1)
btn_5 = tk.Button(root, text="5", command=lambda: add_to_calculation(5), width=5, font=("Arial", 14))
btn_5.grid(row=3, column=2)
btn_6 = tk.Button(root, text="6", command=lambda: add_to_calculation(6), width=5, font=("Arial", 14))
btn_6.grid(row=3, column=3)
btn_div = tk.Button(root, text="/", command=lambda: add_to_calculation("/"), width=5, font=("Arial", 14))
btn_div.grid(row=3, column=4)

btn_7 = tk.Button(root, text="7", command=lambda: add_to_calculation(7), width=5, font=("Arial", 14))
btn_7.grid(row=4, column=1)
btn_8 = tk.Button(root, text="8", command=lambda: add_to_calculation(8), width=5, font=("Arial", 14))
btn_8.grid(row=4, column=2)
btn_9 = tk.Button(root, text="9", command=lambda: add_to_calculation(9), width=5, font=("Arial", 14))
btn_9.grid(row=4, column=3)
btn_minus = tk.Button(root, text="-", command=lambda: add_to_calculation("-"), width=5, font=("Arial", 14))
btn_minus.grid(row=4, column=4)

btn_open = tk.Button(root, text="(", command=lambda: add_to_calculation("("), width=5, font=("Arial", 14))
btn_open.grid(row=5, column=1)
btn_0 = tk.Button(root, text="0", command=lambda: add_to_calculation(0), width=5, font=("Arial", 14))
btn_0.grid(row=5, column=2)
btn_close = tk.Button(root, text=")", command=lambda: add_to_calculation(")"), width=5, font=("Arial", 14))
btn_close.grid(row=5, column=3)
btn_plus = tk.Button(root, text="+", command=lambda: add_to_calculation("+"), width=5, font=("Arial", 14))
btn_plus.grid(row=5, column=4)

btn_clear = tk.Button(root, text="C", command=clear_filed, width=11, font=("Arial", 14))
btn_clear.grid(row=6, column=1, columnspan=2)
btn_equal = tk.Button(root, text="=", command=evaluete_calculation, width=11, font=("Arial", 14))
btn_equal.grid(row=6, column=3, columnspan=2)

root.geometry("300x275")
root.mainloop()
```
