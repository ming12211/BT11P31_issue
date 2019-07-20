# BT11P31_issue
2019_05_05 建立
http://www.ni.com/download/labview-run-time-engine-2016/6066/en/

https://www.ni.com/zh-tw/support/downloads/drivers/download.ni-488-2.html#305442

11 void InvertUint8(unsigned char *DesBuf, unsigned char *SrcBuf)
 12 {
 13     int i;
 14     unsigned char temp = 0;
 15     
 16     for(i = 0; i < 8; i++)
 17     {
 18         if(SrcBuf[0] & (1 << i))
 19         {
 20             temp |= 1<<(7-i);
 21         }
 22     }
 23     DesBuf[0] = temp;
 24 } 


