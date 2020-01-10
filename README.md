# FPGA_Final_Project

## Team 5
> 107214005 田惠瑜
> 107321004 蕭名誼
> 107321002 陳靖雯

#### Input / Output to FPGA board
- 8 x 8 LED matrix for displaying live game (lightB,lightG,lightR,whichCol,EN -> 8x8 matrix)


- LED light to record points (win -> LED)


- Seven segments display showing the counter (COMM,LED_seg -> 7 segments display)


- Four bits switch (sw_L,sw_R,shoot -> 4 bit SW)


- Dip switch (pause,back,clear -> dip switch)


- Buzzer to create pleasant atmosphere (beep -> buzzer)



#### Program module description
```verilog=
module project(
    input CLK,
    input sw_L          //底板左移 ,
    input sw_R          //底板右移 ,
    input shoot         //發射球,
    input pause         //暫停 ,
    input [3:0] back    //哪一關卡 ,
    input clear,
    output [7:0] lightR //紅燈 ,
    output [7:0] lightG //綠燈 ,
    output [7:0] lightB //藍燈 ,
    output reg [2:0] whichCol   //哪一排亮, 
    output EN           //enable,
    output reg[7:0] win //得分 ,
    output reg beep     //音樂,
    output reg [3:0] COMM       //哪一個digit要亮 ,
    output reg [6:0] LED_seg    //計時
);

```

