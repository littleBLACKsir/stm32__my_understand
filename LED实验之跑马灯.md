## LED实验之跑马灯

```c
#include "sys.h"		//引入system（系统）的库
#include "delay.h"		//引入delay的函数
#include "usart.h"		//引入关于串口的函数
#include "led.h"		//引入关于led的初始化函数
 int main(void)
 {	
	delay_init();	    //  延时函数初始化 ，包含在    "delay.h"
	LED_Init();		  	//	LED初始化 ， 包含在 	"led.h"	
	while(1)
	{
		LED0=0;			// 0为亮
		LED1=1;
		delay_ms(300);	 //延时300ms
		LED0=1;
		LED1=0;
		delay_ms(300);	//延时300ms
	}
 }
 /*
 int main(void)
{ 
 
	delay_init();		 
	LED_Init();		        
	while(1)
	{
			GPIO_ResetBits(GPIOB,GPIO_Pin_5);  //LED0对应引脚为GPIOB.5拉低，LED点亮	等同于LED0=0;
			GPIO_SetBits(GPIOE,GPIO_Pin_5);    //LED0对应引脚为GPIOB.5拉高，LED熄灭	等同于LED0=1;
			delay_ms(300);  		   //延时300ms
			GPIO_SetBits(GPIOB,GPIO_Pin_5);	  
			GPIO_ResetBits(GPIOE,GPIO_Pin_5); 
			delay_ms(300);                     
	}
} 
*/
```

