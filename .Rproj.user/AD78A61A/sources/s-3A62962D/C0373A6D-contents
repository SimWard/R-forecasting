## 2 - Time series graphics

library(fpp3)

## 2.1 - tsibble objects

# tsibble objects can easily store time series data

y <- tsibble(
  Year = 2015:2019,
  Observation = c(123, 39, 78, 52, 110),
  index = Year
)

# Various transformations and methods can be applied to tsibble objects

PBS %>%
  filter(ATC2 == 'A10') %>% # Filter lets us select rows based on a condition
  select(Month, Concession, Type, Cost) %>% # Select returns specific columns
  summarise(TotalC = sum(Cost)) %>% # summarise lets us combine data across keys
  mutate(Cost_Billions = TotalC/1e6) -> a10


# Reading in csv files

prison <- readr::read_csv('https://otexts.com/fpp3/extrafiles/prison_population.csv')
prison <- prison %>%
  mutate(Quarter = yearquarter(Date)) %>%
  select(-Date) %>%
  as_tsibble(key=c(State, Gender, Legal, Indigenous,),
             index=Quarter)
prison


## 2.2 - Time plots

melsyd_economy <- ansett %>%
  filter(Airports == 'MEL-SYD', Class == 'Economy') %>%
  mutate(Passengers = Passengers/1000)

autoplot(melsyd_economy, Passengers) +
  labs(title='Ansett economy class',
       subtitle='Melbourne-Sydney',
       y='Passengers (\'000)')

autoplot(a10, Cost_Billions) +
  labs(y='$ (millions)',
       title='Australian antidiabetic drug sales')


## 2.3 - Time Series Patterns




