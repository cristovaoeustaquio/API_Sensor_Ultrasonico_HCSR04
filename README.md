#	Ultrasonic Sensor HCSR04-AN

<div align="left">
    <img src="https://img.shields.io/badge/language-c-blue">
    <img src="https://img.shields.io/badge/hardware-stm32-green">
    <img src="https://img.shields.io/badge/license-MIT-blueviolet">
</div>

---

This project is a simple example demonstrate the behavior of the **Ultrasonic Sensor HCSR04** module of the **STM32 NUCLEO-F103RB** kit.

---

##	📖	The Application Note  

All the behavior of the project is described (in Portuguese) in the document [AN_HCSR04_Application_Note.pdf](https://github.com/cristovaoeustaquio/API_Sensor_Ultrasonico_HCSR04/tree/main/doc).

---

##	📩	Example
In these example we used [SSD1306-API ](https://github.com/SL-RU/stm32libs/tree/master/stm32f10x/ssd1306) to show distance mesurements from HCSR04 sensor. To test all functions that runs on MCU we use a internal push button of kit.

### Includes

```c
#include <stdio.h>
#include <string.h>
#include "Ultrassonico.h"
#include "ssd1306.h"
#include "fonts.h"
#include "bitmap.h"
#include "test.h"
```

Inclusion of the libraries.

### Variables

```c
char distancia_cm_str[30];
char distancia_inch_str[30];
uint32_t distancia_cm = 0;
uint32_t distancia_inch = 0;
uint32_t distancia_limite_cm = 10;
```
- string used to print value in centimeters on oled
- string used to print value in inches on oled
- Variable that receives mesured value from sensor converted to centimeters
- Variable that receives mesured value from sensor converted to inches
- Variable that defines limit distance to trigger alert

### API Functions

```c
uint32_t Medir_Distancia_CM(void); 
```
- Returns the distance from object in centimeters
```c
uint32_t Medir_Distancia_INCH(void); 
```
- Returns the distance from object in inches
```c
void Aproximacao(void); 
```
- It will blinks a GPIO, incresing the frequecy when the distance from object is decreasing 
```c
void Alerta_Distancia(uint32_t dist); 
```
- It will generate an interruption when the 'dist' value is reached
```c
void delay_us(uint16_t us);
```
- Use to get time in microsenconds

### Results

An visual result of this example can be seen in this [video](https://youtu.be/CNuhxgeYytc)
