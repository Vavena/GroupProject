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
  close = Button(root, text="Домой", command=root.destroy)
  close.place(x=150, y=160, width=50, height=30)
  pclbl = Label(root, text=("Компьютер выбрал:"))
  pclbl.place(x=150, y=55)
  pclbl1 = Label(root, text=(" "))
  pclbl1.place(x=150, y=75)

  def exit(y):
    exit()
  def btn_click(choise):
    pclbl = Label(root, text=("Компьютер выбрал:"))
    try: pclbl.configure(text = " ")
    except: print("")

    comp_choise = rdm.randint(1, 3)
    choisedict = {1: "камень", 2: "ножницы", 3: " бумагу"}
    if choise == comp_choise:
      lbl.configure(text="Ничья, тренируйтесь.")
      pclbl1.configure(text=choisedict.get(comp_choise))
    elif ( choise == 1 and comp_choise == 2) or (choise == 2 and comp_choise == 3) or (choise == 3 and comp_choise == 1):
      lbl.configure(text="Вы победили!")
      pclbl1.configure(text=choisedict.get(comp_choise))
    else:
      lbl.configure(text="Вы проиграли...(")
      pclbl1.configure(text=choisedict.get(comp_choise))

    del comp_choise

root.geometry("400x200+200+200")
root.title("Камень, ножницы, бумага")
root.resizable(True, True)
root.mainloop()


![image](https://github.com/Vavena/GroupProject/assets/166173127/62c9eeaf-0a26-48f6-8086-04e438986699)
![image](https://github.com/Vavena/GroupProject/assets/166173127/115c364e-1897-4a2c-8a1f-9a727dce47b6)
![image](https://github.com/Vavena/GroupProject/assets/166173127/24975857-a583-4c31-a127-5eb35f922115)






