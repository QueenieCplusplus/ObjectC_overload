# ObjectC_overload
藉由方法多載實現類別的多型功能

多型的意思是相同訊息傳入後，給不同物件(同名方法的多載)，會引發不同的動作和結果。例如父親類別稱為動物，其中有方法稱為叫，然而子類別分別為貓咪與狗狗，則繼承來的叫，會呈現不同聲音的結果。

                              覆寫方法 override
                            /
                    編譯時期 
                  /         \ 
              多型             方法多載 overload
                  \
                    運行時期

以下僅示範多載的實作，同一類別中，宣告並定義兩個相同名稱的方法。

QQQ.h

           #import <Foundation/Foundation.h>
           
           @interface QQQ: NSObject
           {
              int p;
           }
           
           -(void)setP: (int)k;
           -(int) setP;
           -(void)printP;
           
           @end

QQQ.m

           #import "QQQ.h"
           
           @implementation QQQ
           
           -(void)setP: (int)k
           {
              p = k;
           }
           
           
           -(int) setP
           {
              return p;
           }
           
           
           -(void)printP
           {
              NSLog(@"%i",p);
           }
          
           @end

main.h

          #import<Foundation/Foundation.h>
          #import"QQQ.h"
          
          int main(int argc, const char * argv[])
          {
          
            QQQ *q=[[QQQ alloc]init];
          
            [q setP: 99];
            
            [q setP];
            
            [q printP];   
          
                 return 0;
          
          }
