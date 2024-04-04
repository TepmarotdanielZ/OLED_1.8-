# 1. ST7735 1.8″ TFT Display with STM32

n this tutorial, I will cover how to interface ST7735 1.8″ TFT Display with STM32, and to do so, I will use the SPI peripheral of STM32.
This particular display uses 8 pins for controlling the display, and the pins are shown below

  1. LED :: Backlight -> Connect to 3.3V
  2. SCK :: Serial clock input -> connect to SPI SCK pin
  3. SDA :: Serial data input -> Connect to SPI MOSI pin
  4. DC :: Data/Command selection -> Connect to PA9
  5. RESET :: Reset -> Connect to PC14
  6. CS :: Chip Select -> Connect to PB6
  7. GND :: Ground -> GND
  8. VCC :: Power Supply -> 3.3V


![image](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/eda4e2f3-d7af-4cbb-adf3-eb1c3c7997ab)


# 2. Configuration CubeMX STM32

    . RCC :

![image_2024-04-04_07-27-02](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/a82686ff-b80f-4418-a1d3-8c6e64738d61)

    . SYS :

![image_2024-04-04_07-27-25](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/7d8ca20e-e4d9-4f4e-8582-c3d4368768e2)

    . CLOCK :

![image_2024-04-04_07-27-41](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/2db7f15e-e5c2-4aa0-91cf-7f058d35271d)

    . SPI1 :

![image_2024-04-04_07-28-07](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/4b2d9f31-066e-4d20-8b3b-9bba5ac5af46)

I have selected SPI for the purpose, and I am keeping the Baud Rate around 10.5 MB/s. You can test higher baud rates also.

Other than SPI pins, we need to select three more pins as output. I have selected PB6 for CS, PC14 for RESET, and PA9 for DC. You are free to choose any other pins also, whatever suits the requirement

Other than this, you also need to include ST7735.h and ST7735.c in the project folder.

That’s all the setup needed here. Let’s take a look at some part of the code

    . GPIO :
    
![image_2024-04-04_07-28-49](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/8ebb36e1-d229-4fc4-8f4e-8db400a0a87c)

# 3. CODE :


![image_2024-04-04_07-32-46](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/4f6067f2-d7d9-4111-bc26-0931f1c90e02)


![image_2024-04-04_07-33-03](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/2871da30-4fce-46c5-a907-8ed5ca5c7b8c)


![image_2024-04-04_07-33-17](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/64277a49-9bd4-46b8-8a47-74b18593a6a6)


![image_2024-04-04_07-33-35](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/43159fea-ede4-4862-9fab-d6ce710c9608)

# 4. Schematic Connection :

# 5. Result Testing :

![image](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/8c6cc3a0-22fe-4af4-a5ff-890bd620a721)


![image](https://github.com/TepmarotdanielZ/OLED_1.8-/assets/139426571/61997777-b3ba-48c4-ad98-bb2853d34f8a)


