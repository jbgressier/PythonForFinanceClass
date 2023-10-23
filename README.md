# PythonForFinanceClass
ticker = "AAPL"
opening_price = 144.7
closing_price = 145.2
volume = 1500000
print(ticker, opening_price, closing_price, volume)

ticker = "EUR/USD"
buying_rate = 1.1685
selling_rate = 1.1690
print(ticker, buying_rate, selling_rate)

stocks = ["BNP", "SGCIB", "CACIB"]
stocks.append("CIC")
print(stocks)
stocks.append("HSBC")
print(stocks)

stock_details = {
    "ticker": "AAPL",
    "opening_price": 144.7,
    "closing_price": 145.2,
    "volume": 1500000
}
print(stock_details)

bond_details = {
    "issuer": "Blackrock",
    "maturity date": 10,
    "coupon rate":5,
    "face value": 1000
}
print(bond_details)

stock_prices = [105, 107, 104, 106, 103]
daily_returns = []
for i in range(1, len(stock_prices)):
    daily_return = (stock_prices[i] - stock_prices[i-1]) / stock_prices [i-1]
    daily_returns.append(daily_return)
print(daily_return)
average_return = sum(daily_returns) / len(daily_returns)
print(average_return)

principal = 600
rate = 0.08
years = 0
while principal < 1000:
    principal *= (1 + rate)
    years += 1
print(years)

principal = 600
rate = 0.08
years = 0
while principal < 1000 :
    principal *= (1+rate)
    years += 1
print (principal)

bond_yield = 3.5
if bond_yield > 4.0:
    print("Buy the bond.")
else:
    print ("Sell the bond.")

pe_ratio = 20
if pe_ratio < 15:
    print("Buy the stock.")
elif pe_ratio > 25:
    print("Sell the stock.")
else:
      print("Hold the stock.")

bond_yield = 4.0
if bond_yield >= 4.0:
    print("Buy the bond.")
else:
    print("Do not buy the bond.")

pe_ratio = 17
if 14 <= pe_ratio <= 16:
    print("Buy the stock.")
elif 23 <= pe_ratio <= 27:
    print("Sell the stock.")
else:
    print("Hold the stock.")


class Bond:
    def __init__(self, par_value, coupon_rate, maturity):
        self.par_value = par_value
        self.coupon_rate = coupon_rate
        self.maturity = maturity
    def current_yield (self, market_price) :
        return (self.coupon_rate*self.par_value)/market_price
ten_year_note = Bond(1000, 0.025, 10)
yield_on_note = ten_year_note.current_yield(950)
print(yield_on_note)
class Stock :
    def __init__ (self, name, current_price, dividend):
        self.name = name
        self.current_price = current_price
        self.dividend = dividend
    def yield_dividend (self):
        return (self.dividend / self.current_price)
aapl_stock = Stock ("AAPL", 200, 3)
amzn_stock = Stock ("AMZN", 128, 2)
print ("Apple Stock yield dividend:",aapl_stock.yield_dividend())
print ("Amazon Stock yield dividend:",amzn_stock.yield_dividend())

class Portfolio :
    def __init__ (self):
        self.instruments = []
    def add_instrument (self, name, price):
        instrument = {"name": name , "price": price}
        self.instruments.append(instrument)
    def total_value (self) :
        total_value = 0
        for instrument in self.instruments:
            total_value += instrument ["price"]
        return total_value

portfolioA = Portfolio()
portfolioA.add_instrument("OAT 10 ans", 1000)
portfolioA.add_instrument("AAPL", 200)
portfolioA.add_instrument("AMZN", 128)

portfolio_value = portfolioA.total_value()
print("Total PortfolioA Value:", portfolio_value)

class CurrencyConverter:
    def __init__(self):
        self.rates = {}

    def add_conversion_rate(self, source_currency, target_currency, rate):
        self.rates[(source_currency, target_currency)] = rate

    def convert(self, amount, source_currency, target_currency):
        if (source_currency, target_currency) in self.rates:
            rate = self.rates[(source_currency, target_currency)]
            converted_amount = amount * rate
            return converted_amount
        else:
            return None

converter = CurrencyConverter()
converter.add_conversion_rate("EUR", "USD", 1.07)
converter.add_conversion_rate("EUR", "GBP", 0.87)
converter.add_conversion_rate("USD", "EUR", 0.94)
converter.add_conversion_rate("USD", "GBP", 0.82)
converter.add_conversion_rate("GBP", "EUR", 1.15)
converter.add_conversion_rate("GBP", "USD", 1.22)

amount_to_convert = 200
source_currency = "GBP"
target_currency = "USD"
converted_amount = converter.convert(amount_to_convert, source_currency, target_currency)

if converted_amount is not None:
    print(f"{amount_to_convert} {source_currency} is equal to {converted_amount} {target_currency}")
else:
    print(f"Conversion rate not available for {source_currency} to {target_currency}.")

import numpy as np
days = 1000
mean_daily_return = 0.001
standard_deviation = 0.02
initial_price = 100

daily_returns = np.random.normal(mean_daily_return, standard_deviation, days)

stock_prices = [initial_price]

for r in daily_returns:
    stock_prices.append(stock_prices[-1] * (1 + r))

final_stock_price = stock_prices[-1]

print("First 10 Daily Returns:", daily_returns[:10])
print("First 10 Days of Stock Prices:", stock_prices[:10])
print(f"The final stock price after 1000 days is: ${final_stock_price:.2f}")

