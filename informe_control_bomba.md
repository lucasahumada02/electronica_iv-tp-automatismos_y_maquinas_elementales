# Informe de Desarrollo de un Controlador Digital de Bomba de Agua

Electrónica IV - TP - Automatismos y Máquinas Elementales

## Introducción

El controlador de bomba de agua se trata de una compuerta logica de cuatro entradas donde se busca que active la señal de salida cuando la misma requiera dependiendo de la situacion del tanque de agua y de la cisterna segun los sensores implementados en los mismos. Se trata de dos compuerta AND de dos entradas y una compuerta NAND.

## Metodología de trabajo

La metodologia de trabajo se baso en hacer una tabla de verdad donde se verifico la salida del mismo, osea cuando la bomba deberia estar encendida o apagada. En segundo lugar se opto por hacer un mapa de karnaugh para minimizar el circuito y de esta forma encontrar el circuito final.

## Resultados

El cicuito funciona de forma que mientras cisternaL este apagado la bomba no se puede encender, por lo tanto cuando el nivel de la cisterna suba encendiendo cisternaL y cistenaOK, la bomba se activara de modo automatico si el sensor de tanqueMinimo se encuentra apagado hasta que cistenerOK se apague o tanqueMaximo se encienda.
El circuito queda de la siguiente forma.
![control_bomba](https://github.com/lucasahumada02/electronica_iv-tp-automatismos_y_maquinas_elementales/assets/166075187/f9601998-43a3-43a3-90c9-4812e9213d0c)


## Conclusiones

> Aquí, usando argumentos basados en lo antes presentado, explicas que tipo de máquina es el controlador de bomba de agua (automatismo, máquina elemental o computadora).
