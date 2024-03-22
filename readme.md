# Electrónica IV - TP - Automatismos y Máquinas Elementales

Este trabajo práctico (TP) debe realizarse en modalidad *individual*.

## 1. Objetivos Generales

Para completar con éxito este trabajo práctico deberás

1. Diseñar y observar el funcionamiento de un control de bomba de agua
2. Diseñar y observar el funcionamiento de una unidad aritmética lógica
3. Comunicar tus resultados mediante informes (modelo en apéndice)

## 2. Requisitos

Para completar este trabajo debes

1. Contar con acceso a una computadora (si no cuentas con una se te facilitará el acceso).
2. El programa [Digital](https://www.github.com/hneeman/digital) correctamente instalado.
3. El sistema de control de versiones [git](https://git-scm.com) instalado.
4. Una cuenta en el servicio [GitHub](https://github.com)
5. Opcional, pero muy recomendado. El editor de texto [Visual Studio Code](https://code.visualstudio.com) instalado.

## 3. Procedimiento

Antes de comenzar debes realizar un *fork* de este repositorio en tu cuenta de github. Luego clonarás dicho fork en tu máquina local donde realizarás tu trabajo. Debes hacer commit de los cambios cada vez que avanzas en la solución, y asegurarte de hacer push hacia la versión en la nube antes de entrgar el trabajo. Es buena práctica realizar pull a tu copia local antes de cada sesión de trabajo y push a la nube al finalizar cada sesión.

En este repositorio encontrarás los siguientes documentos.

1. `readme.md` Este documento
2. `informe_control_bomba.md` Informe de desarrollo del controlador de bomba de agua
3. `control_bomba.dig` Esquemático del controlador de bomba de agua que debes completar
4. `informe_unidad_aritmetica_logica.md` Informe de desarrollo de la unidad aritmética lógica
5. `unidad_aritmetica_logica.dig` Esquemático de la unidad aritmética logica que debes completar
6. `sim_control_bomba.dig` Esquemático con simulación para observar el funcionamiento del controlador de bomba de agua
7. `sim_unidad_aritmetica_logica.dig` Esquemático con simulación para observar el funcionamiento de la máquina elemental
8. `bomba.dig` Componente auxiliar para simulación
9. `tanque.dig` Componente auxiliar para simulación

Para completar el práctico deberás completar los esquemáticos de los archivos 3 y 5 con tu implementación y escribir los correspondientes informes (archivos 2 y 4) según los modelos proporcionados.

**Importante:** *Antes de comenzar deberás leer atentamente los enunciados particulares de las secciones 4 y 5*.

## 4. Controlador de bomba de agua

En una instalación de agua corriente hay una cisterna y un tanque elevado. Una electrobomba bombea agua de la cisterna al tanque de agua. En la cisterna hay dos sensores electrónicos de nivel de agua, *cisternaL* y *cisternaOK*. El tanque elevado posee dos sensores, *tanqueL* y *tanqueH*. Los sensores de nivel producen una señal lógica alta cuando el nivel del agua es al menos el nivel del sensor.

|Sensor         | Condición                                                                      |
|---------------|--------------------------------------------------------------------------------|
| *cisternaL*   | Debajo de este nivel la bomba no puede estar encendida porque puede descebarse |
| *cisternaOK*  | Nivel suficiente para encender la bomba de agua                                |
| *tanqueL*     | Debajo de este nivel de agua es necesario llenar el tanque                     |
| *tanqueH*     | Es el máximo nivel que puede alcanzar el tanque sin rebalsar                   |

El objetivo del sistema de control es mantener el nivel del tanque de agua entre *tanqueL* y *tanqueH*, siempre y cuando haya agua suficiente, protegiendo la bomba de agua para evitar que se descebe, lo que haría necesaria la intervención humana.

### 4.1. Objetivos Para Controlador de Bomba de Agua

Debes *implementar el controlador* en el esquemático `control_bomba.dig`. La simulación `sim_control_bomba.dig` demuestra el funcionamiento del controlador en una simulación interactiva. Debes *completar el informe* `informe_control_bomba.md` explicando el proceso seguido, bibliografía consultada y resultados obtenidos.

## 5. Unidad aritmética Lógica (ALU)

La unidad aritmética lógica (ALU por su sigla en inglés) es un circuito lógico que permite realizar operaciones aritméticas y lógicas. En nuestro caso entre señales binarias de dieciseis bit. La Tabla 5-1 muestra las señales de entrada y salida de la ALU.

Tabla 5-1: Señales de entrada y salida de la ALU

| Señal | Modo      | Tipo              | Función   |
|-------|-----------|-------------------|-----------|
| A     | Entrada   | Vector de 16 bit  | Operando  |
| B     | Entrada   | Vector de 16 bit  | Operando  |
| resta | Entrada   | Señal de un bit   | Control   |
| logica| Entrada   | Señal de un bit   | Control   |
| and   | Entrada   | Señal de un bit   | Control   |
| R     | Salida    | Vector de 16 bit  | Resultado |

La ALU soporta las siguientes operaciones:

1. Suma de señales A y B interpretadas como números binarios naturales o complemento a dos
2. Resta de señales A y B interpretadas como números binarios naturales o complemento a dos
3. Suma lógica (and) entre señales A y B
4. Suma lógica entre A y B negado
5. Producto lógico (or) entre señales A y B
6. Producto lógico entre A y B negado

La Tabla 5-2 muestra las configuraciones de las señales de control que permiten ejecutar cada operación soportada.

Tabla 5-2: Modos de operación

| resta | logico | and | resultado         |
|-------|--------|-----|-------------------|
| 0     | 0      | -   | $A + B$           |
| 1     | 0      | -   | $A - B$           |
| 0     | 1      | 0   | $A \vee B$        |
| 1     | 1      | 0   | $A \vee \bar{B}$  |
| 0     | 1      | 1   | $A \wedge B$      |
| 1     | 1      | 1   | $A \wedge \bar{B}$|

### 5.1. Objetivos Para Unidad aritmética Logica

Debes *implementar la ALU* en el esquemático `unidad_aritmetica_logica.dig`. La simulación `sim_unidad_aritmetica_logica.dig` demuestra el funcionamiento de la ALU en forma interactiva. Debes *completar el informe* en `informe_unidad_aritmetica_logica.md` explicando el proceso seguido, la bibliografía consultada y los resultados obtenidos.

## 6. Entrega

Entregarás este práctico enviando como solución a la tarea planteada en el aula virtual un enlace a tu fork de este repositorio en github, asegurándote que su contenido haya sido debidamente actualizado.
