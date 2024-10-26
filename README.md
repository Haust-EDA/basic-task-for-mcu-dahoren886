[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/rtPGwteW)
# First_Task
First_Task for C

如下图所示为流水灯控制原理图，请使用C语言编写逻辑代码，实现从左到右的流水灯，间隔时间为500ms。

![water_led](image.png)

示例代码如下：请在 task.c 中编写你的代码。


```
void delay_ms(unsigned int x)  // 延时函数
{
    unsigned int i,j;
    if(x==1000)
    {
        for(i=0;i<19601;i++)//延时1s
        {
            for(j=5;j>0;j--);
        }
    }
    else while(x--)for(j=115;j>0;j--);
}

// tips: 原理图当中led为低电平点亮，比如点亮LED2,代码为： P0 = 0xFE (1111 1110)


int main(void)
{
   // 编写你的代码
unsigned char led_code[] = {0xfe, 0xfd, 0xfb, 0xf7, 0xef, 0xdf, 0xbf, 0x7f};  // 定义流水灯的控制码
    unsigned char i;

    while (1)
    {
        for (i = 0; i < 8; i++)  // 从左到右依次点亮
        {
            P0 = led_code[i];  // 输出控制码点亮相应的灯
            delay_ms(500);  // 延时 500ms
        }
    }
    
    
    return 0;
}
```

