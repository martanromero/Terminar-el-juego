# Terminar-el-juego
import random
mejores_puntuaciones = {1: [], 2: [], 3: [], 4: []}
def adivinar_numero(nivel):
    if nivel == 1:
        numero_secreto = random.randint(0, 100)
        intentos_maximos = 10
    elif nivel == 2:
        numero_secreto = random.randint(0, 1000)
        intentos_maximos = 20
    elif nivel == 3:
        numero_secreto = random.randint(0, 1000000)
        intentos_maximos = 30
    elif nivel == 4:
        numero_secreto = random.randint(0, 1000000000000)
        intentos_maximos = 40
    else:
        print("Nivel no válido")
        return
    print("Bienvenido al nivel {nivel}- Adivina el número secreto")
    for intento in range(1, intentos_maximos + 1):
        intento_usuario = int(input("Intento{}/{} - Ingresa tu número:".format(intento, intentos_maximos)))
        if intento_usuario == numero_secreto:
            print("Felicidades. Has adivinado el número en {} intentos.".format(intento))
            break
        elif intento_usuario < numero_secreto:
            print("El número es mayor. Intenta de nuevo.")
        else:
            print("El número es menos. Intenta de nuevo.")
    else:
        print("Has agotado todos tus intentos. El número secreto era ¨{}" .format(numero_secreto))
if __name__ == "__main__":
    print("Bienvenido al juego de adivinanza")

    while True:
        print("/Niveles de dificultad:")
        print("1. Nivel simple (0-100)")
        print("2. Nivel intermedio (0-1000)")
        print("3. Nivel avanzado (0-1000000)")
        print("4. Nivel avanzado (0-1000000000000)")
        print("0. Salir")
        seleccion = int(input("Ingresa el número de nivel o 0 para salir:"))

        if seleccion == 0:
            print("¡Hasta luego!")
            
            print("Mejores puntuaciones:")
            for nivel, puntuaciones in mejores_puntuaciones.item():
                print("Nivel (nivel): (puntuaciones)") 
            break
        else:
            adivinar_numero(seleccion)
