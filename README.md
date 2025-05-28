code

x <- c(580, 7813, 28266, 59287, 75700, 87820, 95314, 126214, 218843, 471497, 936851, 1508725, 
2072113)  
library(lubridate)  
png(file ="predictiveAnalysis.png")  
mts <- ts(x, start = decimal_date(ymd("2020-01-22")), frequency = 365.25 / 7)  
plot(mts, xlab ="Weekly Data of sales", ylab ="Total Revenue", main ="Sales vs Revenue", 
col.main ="darkgreen")  
dev.off()


Forecasting Data: 
x <- c(580, 7813, 28266, 59287, 75700, 87820, 95314, 126214, 218843, 471497, 936851, 1508725, 
2072113)       
library(lubridate)         
library(forecast)        
png(file ="forecastSalesRevenue.png")        
mts <- ts(x, start = decimal_date(ymd("2020-01-22")), frequency = 365.25 / 7)  
fit <- auto.arima(mts)     
forecast(fit, 5)       
plot(forecast(fit, 5), xlab ="Weekly Data of Sales", ylab ="Total Revenue", main ="Sales vs 
Revenue", col.main ="darkgreen")         
dev.off()  

install.packages("lubridate")
R 4.5.0
