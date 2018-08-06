---
title: P5 Matriks API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - C++
  
Supported Platform: # must be one of https://git.io/vQNgJ
  - ESP8266 with Arduino IDE

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:

search: true
---

# Introduction

Berikut adalah library untuk arduino yang dapat digunakan di Running text berupa P5 dengan resolusi 64x32. Bahasa pemrograman yang digunakan adalah C++. Library ini memanfaatkan library dari [PxMatrix](https://github.com/2dom/PxMatrix). Fitur yang ditambahkan di sini yakni membuat scrolling text ke arah kiri, dan menampilkan peringatan.

Dokumentasi library ini dibuat dengan [Slate](https://github.com/lord/slate).


# Setup

You should run all of this once, to define the information of your matrix

## Initialize display
Change n with scan rate of your matrix LED.

```C++
#include "DISPLAYCONFIG.h"

dummis::display->begin(n)

``` 

### Function Parameters

Parameter | Description
--------- | -----------
n         | scan rate of your matrix ex: 1/16 scan rate, so input n as 16.

## Configuration the display

```C++
#include "DISPLAYCONFIG.h"
dummis::display->setFastUpdate(param1);
dummis::display->setTextWrap(param2);
dummis::display->setTextSize(param3); 

```

this part is used to change the display configuration, and can be used multiple times if you want to change it.

### Function Parameters

Parameter | Description
--------- | -----------
param1 | set the display to fast update if this true, otherwise if this false.
param2 | set the display to wrap the text if they not fit if this true, otherwise it wont
param3 | set the display to set the size of text displayed in display, the parameter must positive integer.

## Clear the display

```C++
#include "DISPLAYCONFIG.h"
dummis::display->clearDisplay();

```
This is how to clear the display

#Processing Data

##parsing json data
Function to parse the json data, based on two parameter that defined in DISPLAYCONFIG.h like this

```C++
#define PARAMETER1 "Availibility"
#define PARAMETER2 "Down Line"
```
This is the code to used in your project

```C++
#include "DISPLAYCONFIG.h"
String *var = parsJson(String obj);
```
