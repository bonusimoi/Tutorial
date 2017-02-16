//+------------------------------------------------------------------+
//|                                                         NEWS.mq4 |
//|                        Copyright 2017, MetaQuotes Software Corp. |
//|                                             https://www.mql5.com |
//+------------------------------------------------------------------+
#property copyright "Copyright 2017, MetaQuotes Software Corp."
#property link      "https://www.mql5.com"
#property version   "1.00"
#property strict
//+------------------------------------------------------------------+
//| Expert initialization function                                   |
//+------------------------------------------------------------------+
int OnInit()
  {
//---
   EventSetMillisecondTimer(500);
//---
   return(INIT_SUCCEEDED);
  }
//+------------------------------------------------------------------+
//| Expert deinitialization function                                 |
//+------------------------------------------------------------------+
void OnDeinit(const int reason)
  {
//---
   
  }
//+------------------------------------------------------------------+
//| Expert tick function                                             |
//+------------------------------------------------------------------+

#ifdef __MQL4__
    #import "signal.dll" 
    int  signal_open(int &n1, int &n2, int &n3, int &n4, int &type, int &sila); 
    #import
#endif

void OnTimer()
  {
//---
      while(IsStopped()==false) {
      int n1;
      int n2;
      int n3;
      int n4;
      int type;
      int sila;
         signal_open(n1, n2, n3, n4, type, sila);
         if(type!=0)
         {
               Print(n1, " ", n2, " ", n3, " ",n4," ", type, " ", sila);
         }
      Sleep(10);
      }
  }
//+------------------------------------------------------------------+
