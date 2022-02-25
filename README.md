# Google-Stock-Time-series-Data
Google Stock Time series Data 
> inital.vol<-Google$Volume
> recorded_date1<-Google$Date
> recorded_date2<-as.Date(recorded_date1)
> recorded_date<-as.Date(recorded_date2, format= "%y-%m-%d")
> summary(recorded_date)
> Google_Vol<-ts(Google[,6], start=2006-01-03, frequency=12)
> head(Google_Vol,n=240)
> library(TSA)
> library(tseries)
> library(ggplot2)
> library(forecast)
> adf.test(G.Vol)
> plot(G.Vol)
> win.graph()
> ggseasonplot(G.Vol)
> Google_Fit<-auto.arima(G.Vol)
> checkresiduals(Google_Fit)
> tsdiag(Google_Fit)
> Google_Forecast<-forecast(G.Vol,model=Google_Fit)
> plot(Google_Forecast)