# Orlando_Romero_proyectoM3.py
Máquina de Galton

#The following  codigo describe como es funciona una maquina de Galtom
#donde las 3000 canicas pueden moverse hacia la izquierda o derecha



#Numeric Python library
import numpy as np


#Random number library
import random


#Plotting libary
from matplotlib import pyplot as plt


#Number of canicas: elegidas 3000 en este caso
N_canicas= 3000


#probability de que una canica caiga hacia el lado derecho o izquierdo.
#Set to 0.5, meaning that  la canica se mueva
#izquierdo o derecho
prob = 0.5



#Define the random walk function.  N in this case is the number of  canicas
#p is the probablity threshold of goin hacia la izquierda o derecha
#that will describe the marker and line style for  las canicas
def SimpleRandomWalk(N, p, line):


    #Create an array of positions for the walker.  And initialize the first position
   be the origin (zero).  The array will be the same size as the number of  canicas
    #A position counter variable is also used, which is initialized to zero as well.
    position = np.empty(N)
    position[0] = 0
    pos_counter = 0

   containing the full range of the number of possible  canicas
    canicas =  np.arange(N)


    #Start the random walk.
    for i in range(1,N):


        2nerate a random probability value between 0 and 1
        test = random.random()


        #Chechk the value of the probability generated.  If it is > or equal to 0.5, increment the step forwards.
        #If it is less than 0.5, increment a step backwards instead.  Keep track of the position counter after
        #updating it.
        if test >= p:
            pos_counter += 1
        else:
            pos_counter -= 1

        #Fill the current position array index with the current value of the position counter from the loop.
        position[i] = pos_counter



    #Generate a plot of walker position vs. the number of steps taken.  Line is a string that will describe the
    #markers and line type used to plot the random walk.
    plt.plot(steps, position, line)
    plt.xlabel('Steps taken')
    plt.ylabel('Distance from Starting Position')


    return None


#Create a new figure to plot th 
plt.figure()
