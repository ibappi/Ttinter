# Ttinter
## Library 
### [Tutorial Link:](https://www.youtube.com/watch?v=eRaO35fvsHs&list=PLS1QulWo1RIY6fmY_iTjEhCMsdtAjgbZM&index=8)

```
from tkinter import *
from PIL import Image, ImageTk
from tkinter import filedialog
from program import *

window = Tk()
window.geometry("400x600")
window.title("Facial Recognition System")


def exit_window():
    exit()


def image_data():
    pass


def open_image():
    file_path = filedialog.askopenfilename(title='Select an image',
                                           filetypes=[('Image files', '*.png *.jpg *.jpeg *.gif *.bmp *.ico')])
    if file_path:
        display_image(file_path)
        model_run(file_path)


def display_image(file_path):
    image = Image.open(file_path)
    image = image.resize((200, 200))
    photo = ImageTk.PhotoImage(image)
    image_label=Label(window, image=photo)
    image_label.image = photo
    image_label.place(x=100, y=130)

label1 = Label(window, text='Input Image: ', width=20, font=('arial', 14))
label1.place(x=5, y=90)

input_image = Button(window, text='Input Image', width=12, bg='brown', fg='white', command=open_image)
input_image.place(x=190, y=90)

run_button = Button(window, text='Apply Model', width=12, bg='brown', fg='white', command=model_run)
run_button.place(x=20, y=380)

quit_button = Button(window, text='Quit', width=12, bg='brown', fg='white', command=exit_window)
quit_button.place(x=280, y=380)

window.mainloop()

```

