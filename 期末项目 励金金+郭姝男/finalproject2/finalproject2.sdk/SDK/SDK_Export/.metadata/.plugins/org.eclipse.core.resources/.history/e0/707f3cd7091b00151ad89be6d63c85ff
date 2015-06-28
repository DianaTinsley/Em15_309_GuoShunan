#include "xparameters.h"
#include "xgpio.h"
#include "xutil.h"
  

#define LED_DELAY     10000000

//====================================================

int main (void) 
{

    XGpio dip, push,beep,led,outbtn;
	int i, psb_check, dip_check,outbtn_check;
	volatile int Delay;
	int dat = 0x01;
	
    xil_printf("-- Start of the Program --\r\n");
 
    XGpio_Initialize(&dip, XPAR_SW_4BIT_DEVICE_ID);
	XGpio_SetDataDirection(&dip, 1, 0xffffffff);
	
	XGpio_Initialize(&push, XPAR_BTN_4BIT_DEVICE_ID);
	XGpio_SetDataDirection(&push, 1, 0xffffffff);
	
	XGpio_Initialize(&led, XPAR_LED_4BIT_DEVICE_ID);
		XGpio_SetDataDirection(&led, 1, 0x00000000);

		XGpio_Initialize(&outbtn, XPAR_OUTBTN_1BIT_DEVICE_ID);
			XGpio_SetDataDirection(&outbtn, 1, 0xffffffff);

			XGpio_Initialize(&beep, XPAR_BEEP_1BIT_DEVICE_ID);
				XGpio_SetDataDirection(&beep, 1, 0x00000000);


	while (1)
	{
	  psb_check = XGpio_DiscreteRead(&push, 1);
	  xil_printf("Push Buttons Status %x\r\n", psb_check);
	  dip_check = XGpio_DiscreteRead(&dip, 1);
	  xil_printf("DIP Switch Status %x\r\n", dip_check);
	  
	  outbtn_check = XGpio_DiscreteRead(&outbtn, 1);
	  xil_printf("Out Button Status %x\r\n", outbtn_check);


	  if (!outbtn_check) {
	  	              for(i=0;i<4;i++){
	  	              XGpio_DiscreteWrite(&led, 1 , dat);
	  	              for (Delay = 0; Delay < LED_DELAY; Delay++);
	  	              dat = dat <<1;
	  	            XGpio_DiscreteWrite(&beep, 1,0);
	  	              }
	  	              dat = 0x01;
	  	            XGpio_DiscreteWrite(&beep, 1,1);

	  	          }
	  else
		  XGpio_DiscreteWrite(&beep, 1,0);

if(psb_check!=0)
{
	      if(psb_check==0)
	 	  		  XGpio_DiscreteWrite(&led, 1,0);
	 	  if(psb_check==1)
	 		  XGpio_DiscreteWrite(&led, 1,1);
	 	  if(psb_check==2)
	 	  		  XGpio_DiscreteWrite(&led, 1,2);
	 	  if(psb_check==4)
	 	  	  	 XGpio_DiscreteWrite(&led, 1,4);
	 	  if(psb_check==8)
	 	  	  	 XGpio_DiscreteWrite(&led, 1,8);
}


else{
	 	 if(dip_check==0)
	 	 	 	 XGpio_DiscreteWrite(&led, 1,0);
	 	 if(dip_check==1)
	 	 	 	 XGpio_DiscreteWrite(&led, 1,1);
	 	 if(dip_check==2)
	 	 	 	 XGpio_DiscreteWrite(&led, 1,2);
	 	if(dip_check==3)
	 		 	 XGpio_DiscreteWrite(&led, 1,3);
	 	 if(dip_check==4)
	 	 	 	 XGpio_DiscreteWrite(&led, 1,4);
	 	if(dip_check==5)
	 		 	 XGpio_DiscreteWrite(&led, 1,5);
	 	if(dip_check==6)
	 		 	 XGpio_DiscreteWrite(&led, 1,6);
	 	if(dip_check==7)
	 		 	 XGpio_DiscreteWrite(&led, 1,7);
	 	 if(dip_check==8)
	 	 	 	 XGpio_DiscreteWrite(&led, 1,8);
	 	if(dip_check==9)
	 		     XGpio_DiscreteWrite(&led, 1,9);
	 	if(dip_check==10)
	 		 	 XGpio_DiscreteWrite(&led, 1,10);
	 	if(dip_check==11)
	 		 	 XGpio_DiscreteWrite(&led, 1,11);
	 	if(dip_check==12)
	 		 	 XGpio_DiscreteWrite(&led, 1,12);
	 	if(dip_check==13)
	 		 	 XGpio_DiscreteWrite(&led, 1,13);
	 	if(dip_check==14)
	 		     XGpio_DiscreteWrite(&led, 1,14);
	 	if(dip_check==15)
	 		 	  XGpio_DiscreteWrite(&led, 1,15);
}






	  for (i=0; i<9999999; i++); 
	}
 
}
 
