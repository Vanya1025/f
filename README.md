import turtle
from random import randint
v = turtle.Turtle()
v.speed(7)
dots_list = [(0, 80), (40, 80), (40, 120), (80, 120), (80, 250), (140, 250), (140, 100), (170, 100), (170, 200), (210, 200), (210, 140), (230, 140), (230, 90), (270, 90)]
def star():
    for i in range(9):
        v.forward(100)
        v.left(200)

def turtl(dots_list, orienttion):
    if orienttion:
        v.color('black')
        v.fillcolor('grey')
        v.begin_fill()
        for i in dots_list:
            v.goto(i)
        v.goto(270, 0)
        v.goto(0, 0)
        v.goto(0, 80)
        v.end_fill()

        for i in range(5):
            v.begin_fill()
            window()
            v.end_fill()

    else:

        v.fillcolor('black')
        v.begin_fill()
        v.penup()
        v.goto(0, 300)
        v.pendown()
        for i in dots_list:
            v.goto(i)
        v.goto(270, 300)
        v.goto(0, 300)
        v.end_fill()
        for i in range(5):
            v.begin_fill()
            star_drow()
            v.end_fill()



def star_drow():
    v.color('white')
    x_core = randint(0, 270)
    y_core = randint(250, 270)
    v.penup()
    v.goto(x_core, y_core)
    v.pendown()
    for i in range(9):
        v.forward(5)
        v.left(200)


def window():
    v.color('white')
    x_core = randint(100, 120)
    y_core = randint(20, 240)
    v.penup()
    v.goto(x_core, y_core)
    v.pendown()
    for i in range(4):
        v.forward(15)
        v.right(90)


turtl(dots_list, 0)
turtl(dots_list, 1)
turtle.done()
