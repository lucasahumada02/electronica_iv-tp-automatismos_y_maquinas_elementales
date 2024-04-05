# Informe de Desarrollo de un Controlador Digital de Bomba de Agua

Electrónica IV - TP - Automatismos y Máquinas Elementales

## Introducción

El controlador de bomba de agua se trata de una compuerta logica de cuatro entradas donde se busca que active la señal de salida cuando la misma requiera dependiendo de la situacion del tanque de agua y de la cisterna segun los sensores implementados en los mismos. Se trata de dos compuerta AND de dos entradas, una compuerta NAND, una compuerta OR para el clear del flip flop D.

## Metodología de trabajo

La metodologia de trabajo se baso en hacer una tabla de verdad donde se verifico la salida del mismo, osea cuando la bomba deberia estar encendida o apagada. En segundo lugar se opto por hacer un mapa de karnaugh para minimizar el circuito y de esta forma encontrar el circuito final.

## Resultados

El cicuito funciona de forma que mientras cisternaL este apagado la bomba no se puede encender, por lo tanto cuando el nivel de la cisterna suba encendiendo cisternaL y cistenaOK, la bomba se activara de modo automatico si el sensor de tanqueMinimo se encuentra apagado hasta que cistenerOK se apague o tanqueMaximo se encienda. Esto es controlado por un Flip flop D que se limpia cuando esta activo tanqueMaximo y cuando la CisternaOK esta apagada.
El circuito queda de la siguiente forma:
![control_bomba](https://github.com/lucasahumada02/electronica_iv-tp-automatismos_y_maquinas_elementales/assets/166075187/bc09281f-e4cb-415d-a0fb-500b36317779)



## Conclusiones
El controlador de bomba de agua se trata de una maquina de automatismo ya que trabaja de manera automatica dependiendo de las variables de entrada que se introduzcan realizando una tarea especifica sin necesidad de intervenir manualmente.
