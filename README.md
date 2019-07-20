# BT11P31_issue
2019_05_05 建立
http://www.ni.com/download/labview-run-time-engine-2016/6066/en/

https://www.ni.com/zh-tw/support/downloads/drivers/download.ni-488-2.html#305442



131 unsigned short CRC16_X25(unsigned char *puchMsg, unsigned int usDataLen)  
132 {  
133     unsigned short wCRCin = 0xFFFF;  
134     unsigned short wCPoly = 0x1021;  
135     unsigned char wChar = 0;  
136     
137     while (usDataLen--)     
138     {  
139         wChar = *(puchMsg++);  
140         InvertUint8(&wChar, &wChar);  
141         wCRCin ^= (wChar << 8); 
142         
143         for(int i = 0;i < 8;i++)  
144         {  
145             if(wCRCin & 0x8000)
146             {              
147                 wCRCin = (wCRCin << 1) ^ wCPoly; 
148             }            
149             else  
150             {
151                 wCRCin = wCRCin << 1; 
152             }            
153         }  
154     }  
155     InvertUint16(&wCRCin, &wCRCin);  
156     return (wCRCin^0xFFFF) ;  
157 }  
158   
