# Airline-Taxi-Out-time-estimation (Tarmac Delays)

Web scraped 4 months of flight statistics and weather data from 10 different airports to train a model to predict tarmac delays. Used lasso and ridge regularization techniques in addition to polynomial transformations to optimize model performance. The objective of this project was to develop a tool to help air traffic controllers have a better sense of the time an aircraft needs to takeoff.

### Introduction

If you've ever flown out of a congested airport, you've almost certainly encountered a cab time wait. Everyone is on board, the plane has even left the gate, but it's taking a long time to take off.

Taxi time may be defined as the amount of time an aircraft spends moving on the surface of an airport. I solely concentrated on departure taxi-time (or taxi-out time) within the scope of this study, which is the time between an aircraft leaving a terminal gate and actually taking off from an airport. Typically, ATC (Air Traffic Control) supervises the entire procedure, giving pilots authority to depart from the gate, takeoff, and so on.

Taxitime matters because:

![image](https://user-images.githubusercontent.com/47337257/151247755-b5542d99-318d-4836-92dc-b09e53a0e211.png)

A brief look at the ICAO data above indicates that a typical Boeing 777 consumes 23.3 kg/min (or 6.15 gallons/min) of fuel merely taxiing. With an average taxi duration of 15 minutes, this equates to almost 92 gallons of gasoline used simply taxiing out to the takeoff position!
While different types of aircraft consume varying amounts of fuel, being able to optimize airport surface traffic and cut taxi times would help airlines to save money on fuel while also lowering CO2 emissions and enhancing customer experience.

Because a lot of flight data is internal or subjective depending on the airline, I selected to evaluate how the top four airlines fared in taxi-time speed, as well as how weather patterns influenced taxi timings. So my goal may be summed up in the following questions:

- Do taxi times fluctuate depending on the airline?
- Do airport weather conditions have an effect on taxi times, and if so, how much?
- Is it possible to forecast taxi times in order to enhance runway sequencing?

![image](https://user-images.githubusercontent.com/47337257/151253099-a709e4a6-db89-4577-b113-325babd05c25.png)

### Data
To account for seasonality, 10 airports were selected in four separate months (January, April, June, and October) in 2018. I also confined my airlines to the top four (Southwest, American, Delta, and United) because they account for a sizable share of the domestic flying market. I used Selenium to automate the process of getting flight information from the Bureau of Transportation's aviation page, and BeautifulSoup to scrape weather data for related dates and airports.


![image](https://user-images.githubusercontent.com/47337257/151258226-d181095c-32f4-4098-9d1a-c02974cd0f1f.png)



### Approach
1. Scrape flight data from the [Bureau of Transportation Statistics.](https://www.transtats.bts.gov/ONTIME/Departures.aspx)
2. Scrape weather data from [WeatherUnderground](https://www.wunderground.com/history/monthly/us/ca/san-francisco/KSFO/date/2019-1)
3. Clean and pre-process data
4. Modeling and Evaluation


We may deduce from this regression model that taxi times are longer at busier airports and on early flights. While this tendency is logical and may be predicted, it is critical to validate it with facts. Furthermore, this model can more precisely weigh each airport in order to calculate a plane's taxi time.
And, while the reasons for Southwest's dominance in taxi time measurements are unknown, it is something worth investigating in order to identify other elements that might impact tarmac delays.

