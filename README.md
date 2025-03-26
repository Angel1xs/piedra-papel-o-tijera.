import random # holii Abri, ya logre que cuente los puntos, y si teniamos razon era definiendolos como global, te explico

puntoCO = [] #1 elimine el resultado de jugador y de computadora por que quedaban inecesarios ya definiendo las variables globales
puntoJU = []

puntos_computadora = 0 # aqui se quedan estas variables
puntos_jugador = 0

def juego():
    global puntos_computadora, puntos_jugador #2 y aqui las definimos como globales :)
    opciones = ["piedra", "papel", "tijera"]
    
    computadora = random.choice(opciones)
    usuario = input("Elige: piedra, papel o tijera: ")

    print("La computadora eligió: ", computadora)

    if usuario == computadora:
        print("Empate!")
        puntoCO = 0 # agregar puntos al ganador
        puntoJU = 0
    elif (usuario == "piedra" and computadora == "tijera") or \
         (usuario == "tijera" and computadora == "papel") or \
         (usuario == "papel" and computadora == "piedra"):
        print("Ganaste!")
        puntoCO = 0 # agregar puntos al ganador
        puntoJU = 1
        print("punto para el jugagor")
    else:
        print("Perdiste!")
        puntoCO = 1 # agregar puntos al ganador
        puntoJU = 0
        print("punto para la computadora")
        
    puntos_computadora = puntos_computadora + puntoCO #3 aqui ya que ya los tenemos como variables globales es posiblre sumar sin la variable que agregamos de resultado 
    puntos_jugador = puntos_jugador + puntoJU     #contador de puntos
    print(f" los puntos del jugador son:", {puntos_jugador}) #4 por cierto aqui no imprimia por que estaba usando [puntos_jugador] o puntos_jugador asi a secas, para que imprima el resultado, es con {} osea {puntos_jugador]
    print(f" los puntos de la computadora son:", {puntos_computadora})
    continuar = input ("quieres volver a jugar?")
    if continuar == "no":
        print ("adios")
# aun no logro hacer que cierre pero estaba pensando eliminarlo por que es un poco molesto estar todo el tiempo diciendo que quieres continuar, pero no lo se por que se vuelve tedioso que la mayoria de las veces la computadora empata y se vuelve eternoo

    if puntos_jugador == 3:
        print("felicidades, al logrado ganar") # aqui esta el si tienes mas de 3 puntos ganas, pero aun te pide confirmacion de que si quieres volver a jugar y si tienes mas de 3 puntos te dice que has ganado, eso hay que solucionarlo jajaja
        continuarGAJU = input ("quieres volver a jugar?")
        if continuarGAJU == "no":
            print ("adios")
            return

    elif puntos_computadora == 3:
        print("lo siento, a ganado la computadora") # igual aqui abajo
        print("por que no lo intentas de nuevo")
        continuarGACO = input ("quieres volver a jugar?")
        if continuarGACO == "no":
            print ("adios")
            return
        
while True: #mejora de bucle
    if juego():
        print("hasta luego")
        break
