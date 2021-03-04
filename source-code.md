# Youtube-Downloader
#This is a python based GUI type Tool To Download videos from Youtube.
from tkinter import *
from pytube import YouTube


root = Tk()
root.geometry('500x300')
root.resizable(0,0)
root.title("@MuL's video downloader")

Label(root,text = 'Youtube Video Downloader', font ='arial 20 bold',bg = 'yellow').pack()
link = StringVar()
Label(root, text = 'Paste Link Here:', font = 'arial 15 bold',bg = 'Red').place(x= 160 , y = 60)

Label(root, text = '@Mul Video Downloader', font = 'arial 12 bold',bg = 'blue').place(x= 140 , y = 40)

link_enter = Entry(root, width = 70,textvariable = link).place(x = 32, y = 90)

def Downloader():     
    url =YouTube(str(link.get()))
    video = url.streams.first().download(output_path = "D:\\Video's")

    video.download()
    Label(root, text = 'DOWNLOADED', font = 'arial 15',bg = 'purple').place(x= 180 , y = 210)  
Button(root,text = 'DOWNLOAD', font = 'arial 15 bold' ,bg = 'green', padx = 2, command = Downloader).place(x=180 ,y = 150)
root.mainloop()


