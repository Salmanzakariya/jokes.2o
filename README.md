# jokes.2o
import os
import pyjokes
import customtkinter as ctk


def gen():
    a= pyjokes.get_joke()
    print('* '+a ) 
    result.delete("1.0", ctk.END)
    result.insert("0.0",a)
    return
    

root=ctk.CTk()
root.geometry("500x500")

root.title("Python Jokes")

ctk.set_appearance_mode("dark")


title_label =ctk.CTkLabel(root,text='NerD JokeS',font=ctk.CTkFont (size=20,weight='bold'))
title_label.pack(pady=10,padx=20)

frame=ctk.CTkFrame(root)
frame.pack(fill='x',padx=50)

result=ctk.CTkTextbox(frame,font=ctk.CTkFont(size=15))
result.pack(fill='x',padx=5)


button_label=ctk.CTkLabel(frame,text='   ')
button_label.pack()

button=ctk.CTkButton(frame,text="Genarate jokes",command=gen)
button.pack()



root.mainloop()
