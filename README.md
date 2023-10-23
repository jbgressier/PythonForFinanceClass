# PythonForFinanceClass

Lecture 2 :

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
