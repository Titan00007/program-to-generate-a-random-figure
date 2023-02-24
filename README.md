import random
import tkinter 

def draw(event):
    canvas.delete('all')
    
    colors = random.choice(['aqua', 'blue', 'fuchsia', 'green', 'maroon', 'orange',
                      'pink', 'purple', 'red','yellow', 'violet', 'indigo', 'chartreuse', 'lime'])
    x = random.randint(10, 550)
    y = random.randint(10, 550)
    d = random.randint(10, 550)
    if d + x > 600:
        d = 600 - x
    if d + y > 600:
        d = 600 - y
    a = random.randint(1, 3)
    
    if a == 1:
        canvas.create_oval((x, y), (x + d, y + d), fill=colors)
    elif a == 2:
        canvas.create_rectangle((x, y), (x + d, y + d), fill=colors)
    elif a == 3:
        x1 = random.randint(10, 550)
        y1 = random.randint(10, 550)
        x2 = random.randint(10, 550)
        y2 = random.randint(10, 550)
        canvas.create_polygon([x, y], [x1, y1], [x2, y2], fill=colors)

master = tkinter.Tk()
canvas = tkinter.Canvas(master, bg='white', height=600, width=600)
canvas.pack()
master.bind("<KeyPress>", draw)
