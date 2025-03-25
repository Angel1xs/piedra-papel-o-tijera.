import random

listopciones = [1:"piedra", 2:"papel", 3:"tijera"]

resultado_computadora = []
resultado_jugador =[]

puntoCO = []
puntoJU = []


puntos_computadora = 0 
puntos_jugador = 0

def juego():
    opciones = ["piedra", "papel", "tijera"]
    
    computadora = random.choice(opciones)
    usuario = input("Elige: piedra, papel o tijera: ")

    print("La computadora eligió: ", computadora)

    if usuario == computadora:
        print("Empate!")
        puntoCO = 0
        puntoJU = 0
    elif (usuario == "piedra" and computadora == "tijera") or \
         (usuario == "tijera" and computadora == "papel") or \
         (usuario == "papel" and computadora == "piedra"):
        print("Ganaste!")
        puntoCO = 0
        puntoJU = 1
        print("punto para el jugagor")
    else:
        print("Perdiste!")
        puntoCO = 1
        puntoJU = 0
        print("punto para la computadora")
        
    resultado_computadora = puntos_computadora + puntoCO
    resultado_jugador = puntos_jugador + puntoJU     #contador de puntos
    print(f" los puntos del jugador son:", resultado_jugador)
    print(f" los puntos de la computadora son:", resultado_computadora)
    continuar = input ("quieres volver a jugar?")
    if continuar == "no":
        print ("adios")
    
while True: #mejora de bucle
    if juego():
        print("hasta luego")
        break
