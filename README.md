# BT11P31_issue
2019_05_05 建立
http://www.ni.com/download/labview-run-time-engine-2016/6066/en/

https://www.ni.com/zh-tw/support/downloads/drivers/download.ni-488-2.html#305442

36 void InvertUint16(unsigned short *DesBuf, unsigned short *SrcBuf)  
 37 {  
 38     int i;  
 39     unsigned short temp = 0;    
 40     
 41     for(i = 0; i < 16; i++)  
 42     {  
 43         if(SrcBuf[0] & (1 << i))
 44         {          
 45             temp |= 1<<(15 - i);  
 46         }
 47     }  
 48     DesBuf[0] = temp;  
 49 }
