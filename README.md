# Python-Dice-rolling-simulator-GUI
# Import all from tkinter
# into this program
from tkinter import *
# Import Image and ImageTk modules
# from PIL library (pillow library)
# into this program
from PIL import Image, ImageTk
# import random library
# into this program
import random
# Define a function for 
# rolling the dice
# i.e. for changing
# the image on label
def diceRoll() :
    # Select random image from list
    randomImg = random.choice(diceImg)
    img_1 = Image.open(randomImg)
    # open and generated random img
    # as per pillow library 
    img_2 = ImageTk.PhotoImage(img_1)
    # Update image with new image
    imgLabel.configure(image = img_2)
    # Keep a reference
    imgLabel.image = img_2
# Main code
if __name__ == "__main__" :
    # Create a window container
    window = Tk()
    
    # Set background colour of window 
    # container using configure() method 
    # with background attribute
    window.configure(background = 'light green')
    # Set the configuration of window
    # container using geometry() method
    # width X length
    window.geometry("300x310")
    # Set the title of window container
    # using title() method
    window.title("Dice Roll")
    # List of images
    diceImg = ['img/dice1.png', 'img/dice2.png', 'img/dice3.png',
                'img/dice4.png', 'img/dice5.png', 'img/dice6.png']
    # Select random image from list
    randomImg = random.choice(diceImg)
    # Create image object
    # using open() method
    # of image module
    img_1 = Image.open(randomImg)    
    # Create image object for tkinter
    # using PhotoImage() method of
    # ImageTk module.
    # This method take image as
    # an argument
    img_2 = ImageTk.PhotoImage(img_1)
    # Create a image label using Label()
    # and set image in it.
    imgLabel = Label(window, image = img_2)
    # Placing the widgets at respective
    # positions in table like structure
    # using grid() method
    # Place this widget in grid at (2, 2)
    # along with specified padding
    imgLabel.grid(row = 2, column = 2, 
                    padx = "25", pady = "25")
    # Create a Button and attached 
    # function using Button()
    rollButton = Button(window, text = "Roll Dice",
                    bg = "red", fg = "black",
                    command = diceRoll)
    # Place button widget in grid at (3, 2)
    rollButton.grid(row = 3, column = 2,
                    padx = "25", ipadx = "10")
    # Start the window,
    # waiting for events and
    # updating the GUI. 
    window.mainloop()
