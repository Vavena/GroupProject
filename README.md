from tkinter import *
from tkinter import ttk
import random as rdm

root = Tk()

def show_message():
    name = entry.get() +", выберите фигуру"
    window_2(name)

entry = ttk.Entry()
entry.pack(anchor=NW, padx=6, pady=6)

btn = ttk.Button(text="Click", command=show_message)
btn.pack(anchor=NW, padx=6, pady=6)

def window_2(name):
    global btn, entry
    entry.destroy()
    btn.destroy()

    root.resizable(False, False)
    btn = Button(root, text="Камень", command=lambda x=1: btn_click(x))
    btn2 = Button(root, text="Ножницы", command=lambda x=2: btn_click(x))
    btn3 = Button(root, text="Бумага", command=lambda x=3: btn_click(x))
    btn.place(x=10, y=10, width=80, height=50)
    btn2.place(x=10, y=60, width=80, height=50)
    btn3.place(x=10, y=110, width=80, height=50)

    lbl = Label(root, text= name )
    lbl.place(x=150, y=25)

  def btn_click(choise):
    comp_choise = rdm.randint(1, 3)

    if choise == comp_choise:
      lbl.configure(text="Ничья, тренируйтесь.")
    elif ( choise == 1 and comp_choise == 2) or (choise == 2 and comp_choise == 3) or (choise == 3 and comp_choise == 1):
      lbl.configure(text="Вы победили!")
    else:
      lbl.configure(text="Вы проиграли...(")
    del comp_choise

root.geometry("300x200+200+200")
root.title("Камень, ножницы, бумага")
root.resizable(True, True)
root.mainloop()
