# piedra-papel-o-tijera.
se entrega viernes 28/03/25
En eqiuipo realicen 5 mejoras al siguiente código -.

import random

def juego():
    opciones = ["piedra", "papel", "tijera"]
    computadora = random.choice(opciones)
    usuario = input("Elige: piedra, papel o tijera: ")

    print("La computadora eligió: ", computadora)

    if usuario == computadora:
        print("Empate!")
    elif (usuario == "piedra" and computadora == "tijera") or \
         (usuario == "tijera" and computadora == "papel") or \
         (usuario == "papel" and computadora == "piedra"):
        print("Ganaste!")
    else:
        print("Perdiste!")

juego()


Entregables
1. Archivo especificando mejoras
2. Código ejecutalbe .py
