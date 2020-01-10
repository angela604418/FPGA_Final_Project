# FPGA_Final_Project

## Team 5
> 107214005 田蕙瑜
> 107321004 蕭名誼
> 107321002 陳靖雯

#### Input / Output to FPGA board
- 8 x 8 LED
![pic](https://drive.google.com/open?id=1gjqu5B8v7i8cUXpQzY_e0AOqcqWjhE3j"8 x 8 LED") 



#### Program module description
```verilog=
module project(
    input CLK,
    input sw_L//底板左移 ,
    input sw_R//底板右移 ,
    input shoot//發射球,
    input pause//暫停 ,
    input [3:0] back//哪一關卡 ,
    input clear,
    output [7:0] lightR//紅燈 ,
    output [7:0] lightG/綠燈 ,
    output [7:0] lightB//藍燈 ,
    output reg [2:0] whichCol//哪一排亮, 
    output EN//enable,
    output reg[7:0] win//得分 ,
    output reg beep//音樂,
    output reg [3:0] Anode_Activate//哪一個digit要亮 ,
    output reg [6:0] LED_out//計時
);
//sw_L,sw_R,shoot -> 4 bit SW; 
  pause,back,clear -> 指撥開關; 
  lightB,lightG,lightR,whichCol,EN -> 8x8 matrix;
  Anode_Activate,LED_out -> 七段顯示器; 
  win -> LED; 
  beep -> buzzer
```
