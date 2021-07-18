# TFlite micro slide controller demo

This is a demo modified from the Gesture to emoji demo on arduino. https://github.com/arduino/ArduinoTensorFlowLiteTutorials/tree/master/GestureToEmoji

## Intro

The idea is to use gesture to control google slide, as it turns out the easiest way to control without plugin on a computer is to turn it into a USB Keyboard. The reason to use a USB Keyboard instead of a Bluetooth Keyboard is because I can't get the [mbded-ble-hid](https://github.com/tcoppex/mbed-ble-hid) to work. 

As it turns out, this will also useful for anything on pc that also use same key for navication. So I use the up key and down key, to maximize it other uses. 

## Data gathering

As said, this is a modification from the Gesture to Emoji. So I just reuse the script. As you can see at [this repo](https://github.com/sweemeng/tflite-slide-controller-data-collector)

The data I gather is the 

* swipe left
* swipe right 
* swipe down(I don't know why I have this). 

## Training

https://colab.research.google.com/drive/1Sq1QWrrUkoouZurCwOeG84Cpxx128nbE?usp=sharing

Then download the `models.h` also tflite file for backup. 

## The arduino code

The code is here. The difference is, the code is built on platform.io. The tflite micro is built from source. I include it in `lib` directory to make built easy, also included is the `models.h`. 

How this work is, the arduino will read the gesture. If gesture is swipe left, send Page Up key, if swipe right, send page down key. 

## Deploy

It is easier if you use platform.io on VS Code. Else you can run

`pio run --target upload --environment gesture_control`


