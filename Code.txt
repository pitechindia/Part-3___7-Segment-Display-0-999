#include <reg51.h>

#define Port2 P2	// Define Port P2 for 1st Segment 
#define Port3 P3	// Define Port P3 for 2nd Segment 
#define Port0 P0	// Define Port P0 for 3rd Segment

void delay(unsigned int a);		// sub-routine for delay
unsigned int i,j,k;							// Define variables

// Hex code Array for Common Anode 7 Segment Display....
unsigned char segment[]={0xC0,0xF9,0xA4,0xB0,0x99,0x92,0x82,0xF8,0x80,0x90};

void main(void)
	
{
	Port0=0xff;
	Port2=0xff;
	Port3=0xff;
			for(i=0;i<10;i++)
				{
					Port0=segment[i];					// Display according to array index hex code...
					for(j=0;j<10;j++)
						{
							Port3=segment[j];			// Display according to array index hex code...
								for(k=0;k<10;k++)
								{
									Port2=segment[k];	// Display according to array index hex code...
									delay(30);	
								}
						}		
				}
	
	
}		

// Delay Function
void delay(unsigned int a)
{
	unsigned int i,j;
		for(i=0;i<a;i++)
			for(j=0;j<1275;j++)    
				{}
}
