# FPGA_Final_Project
---
## Team 5
> 107214005 田蕙瑜
> 107321004 蕭名誼
> 107321002 陳靖雯

### Input / Output to FPGA board
- 8 x 8 LED matrix for displaying live game (lightB, lightG, lightR, whichCol, EN -> 8x8 matrix)

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/level1.png)

- LED light to record points (win -> LED)

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/points.png)

- Seven segments display showing the counter (COM, LED_seg -> 7 segments display)(4 digits)

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/seg.png)

- Four bits switch (sw_L, sw_R, shoot -> 4 bit SW)

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/switch.png)

- Dip switch (pause, back, clear -> dip switch)

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/clear_pause.png)

- Buzzer to create pleasant atmosphere (beep -> buzzer)



### Four game level
- Level 1

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/level1.png)

- Level 2

![](![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/level2.png))

- Level 3

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/level3.png)

- Level 4

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/level4.png)

### Result Demonstration

- Success picture

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/success.png)

- Fail picture

![](https://github.com/angela604418/FPGA_Final_Project/blob/master/Images/fail.png)

### Function description
- 闖關只有一個球的機會，可左右移動底版以便接球
- 可將球反彈向上敲打磚塊，打擊一個即得一分
- 若在球掉落前累積得到8分則可過關；反之，若在得到8分前讓球掉落至底板以下，即未接到球，則失敗。

### Program module description
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

