---
id: dcaLCQa27jweR8cfy2wn8
title: Lecture 8
desc: ''
updated: 1634538115746
created: 1634535324275
---

# 7 Segment LED and Intro to LCD

> ![](/assets/images/2021-10-18-11-18-49.png)

```c
#include<avr/io.h>

int main()
{
    DDRA = DDRB = 0xFF; // Common Cathode PORTA output
    while(1)
    {
        PORTA = 0x77; // Display A
        PORTB.b0 = 1; // Enable pin
    }
    return 0;
}
```

> ![](/assets/images/2021-10-18-11-28-58.png)

```c
#include<avr/io.h>

int main()
{
    DDRA = DDRB = 0xFF;
    int arr[] = {0x90, 0x80, 0xF8, 0x82, 0x92, 0x99, 0xB0, 0xA4, 0xF9, 0xC0}
    int i;
    while(1)
    {
        PORTB.b0 = 1;
        for(i=0;i<10;i++)
        {
            PORTA = arr[i];
            delay_ms(1000);
        }
    }
    return 0;
}
```

# LCD's
* Pin Position
    * ![](/assets/images/2021-10-18-11-46-36.png)
* Connections with AVR
    * ![](/assets/images/2021-10-18-11-47-39.png)
* Internal Components
    * ![](/assets/images/2021-10-18-11-49-03.png)
* Some important pins
    * ![](/assets/images/2021-10-18-11-50-21.png)
* Pin5 - R/W (Read/Write)
    * 0 means write and 1 means read
* Pin6 - Enable
    * High to low means latch the data.
    * Mimimum pulse width 450ns
* Pin7 - OR DB7
    * 1 means send new information and 0 means not sending new information.
* C program declaration
    * ![](/assets/images/2021-10-18-11-54-05.png)
* C program for LCD Commands
    * ![](/assets/images/2021-10-18-11-56-02.png)
* Table for lcd commands
    * ![](/assets/images/2021-10-18-11-57-33.png)

## Some part left