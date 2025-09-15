import tkinter as tk
from tkinter import ttk
import datetime

def calcular_edad():
    try:
        anio_nacimiento = int(entry_anio.get())
        anio_actual = datetime.datetime.now().year
        edad = anio_actual - anio_nacimiento
        
        if edad >= 0:
            resultado_label.config(text=f"Tu edad es: {edad} años")
        else:
            resultado_label.config(text="El año ingresado no es válido.")
            
    except ValueError:
        resultado_label.config(text="Por favor, ingresa un año válido.")

ventana = tk.Tk()
ventana.title("Calculadora de Edad")

label_anio = ttk.Label(ventana, text="Año de nacimiento:")
entry_anio = ttk.Entry(ventana)

boton_calcular = ttk.Button(ventana, text="Calcular Edad", command=calcular_edad)

resultado_label = ttk.Label(ventana, text="")

label_anio.grid(row=0, column=0, padx=10, pady=10, sticky="e")
entry_anio.grid(row=0, column=1, padx=10, pady=10, sticky="w")

boton_calcular.grid(row=1, column=0, columnspan=2, pady=10)

resultado_label.grid(row=2, column=0, columnspan=2, pady=10)

ventana.mainloop()
