---
layout: post
title: "Weekly Project Post #9"
subtitle: InvestaTrack development updates
date: 2025-07-25
thumbnail-img: /assets/img/IT.png
tags: [project, java, spring-boot, weekly-update]
author: Matthew Presti
---

### What did you do last week?

I made significant progress this week and worked out a lot of bugs! I successfully resolved all the critical relationship and JSON serialization issues that were halting my progress. The breakthrough came from implementing a comprehensive DTO (Data Transfer Object) pattern that eliminated lazy loading exceptions and provided clean API responses.

The major achievement was creating a robust testing infrastructure. I developed an automated test script that seeds the database with realistic portfolio data and validates the complete transaction flow. The test demonstrates 5 transactions across 2 portfolios with proper position tracking, fee calculations, and portfolio value updates. I chose to use a TestDataController with curl commands rather than MockMVC because as a learning project, this approach provided a more straightforward way to understand the complete application flow and validate real database operations without the complexity of mocking frameworks.

I implemented TransactionDTO and PositionDTO classes that provide clean, frontend-ready JSON responses containing only essential data (IDs, names, symbols, amounts) without the bloated nested objects that were causing serialization problems. This approach follows industry practices and eliminates the circular reference issues I was encountering.

The transaction logic is now working which is exciting!

### What do you plan to do this week?

Now that the backend architecture is solid and proven to work, I plan to begin frontend development. The clean DTO responses and well-tested API endpoints provide an excellent foundation for building a React-based user interface. I&#39;ll start with basic portfolio viewing functionality and transaction history displays.

I also want to expand the DTO pattern to other controllers as needed and potentially integrate a real-time stock price API to replace the static prices currently used in testing.

### Are there any impediments in your way?

The major impediments have been resolved. The DTO pattern solved the serialization complexity, and the API test results gives me confidence that the business logic is working correctly. Moving to frontend development will present new learning challenges, but the backend foundation is now stable and production-ready.

### Reflection on the process

The combination of automated testing and DTOs proved to be the optimal approach. The DTO decision eliminated all Jackson serialization complexity while creating clean, maintainable API contracts. This follows professional separation of concerns where internal entity structure can evolve independently from the API interface.


### API Testing Example
```
===== INVESTATRACK API TEST RESULTS =====
Fri Jul 25 19:59:46 MDT 2025

Load Result:
Test data loaded: 2 users, 2 portfolios, 3 stocks, 5 transactions (with auto-created positions)

=== TRANSACTION VERIFICATION ===
All Transactions (Raw Data):
[
  {
    "transactionId": 1,
    "portfolioId": 1,
    "portfolioName": "Growth Fund",
    "stockId": 1,
    "stockSymbol": "AAPL",
    "stockName": "Apple Inc.",
    "transactionType": "BUY",
    "quantity": 10,
    "pricePerShare": 190.23,
    "totalAmount": 1902.30,
    "transactionDate": "2025-07-25T19:59:46.238087",
    "fees": 4.95,
    "description": "BUY 10 shares of AAPL @ $190.23",
    "netAmount": 1907.25
  },
  {
    "transactionId": 2,
    "portfolioId": 1,
    "portfolioName": "Growth Fund",
    "stockId": 3,
    "stockSymbol": "MSFT",
    "stockName": "Microsoft Corp.",
    "transactionType": "BUY",
    "quantity": 5,
    "pricePerShare": 310.00,
    "totalAmount": 1550.00,
    "transactionDate": "2025-07-25T19:59:46.242854",
    "fees": 2.00,
    "description": "BUY 5 shares of MSFT @ $310.00",
    "netAmount": 1552.00
  },
  {
    "transactionId": 3,
    "portfolioId": 1,
    "portfolioName": "Growth Fund",
    "stockId": 3,
    "stockSymbol": "MSFT",
    "stockName": "Microsoft Corp.",
    "transactionType": "SELL",
    "quantity": 2,
    "pricePerShare": 310.00,
    "totalAmount": 620.00,
    "transactionDate": "2025-07-25T19:59:46.245868",
    "fees": 1.00,
    "description": "SELL 2 shares of MSFT @ $310.00",
    "netAmount": 619.00
  },
  {
    "transactionId": 4,
    "portfolioId": 2,
    "portfolioName": "Conservative Fund",
    "stockId": 2,
    "stockSymbol": "GOOGL",
    "stockName": "Alphabet Inc.",
    "transactionType": "BUY",
    "quantity": 5,
    "pricePerShare": 125.45,
    "totalAmount": 627.25,
    "transactionDate": "2025-07-25T19:59:46.247754",
    "fees": 3.95,
    "description": "BUY 5 shares of GOOGL @ $125.45",
    "netAmount": 631.20
  },
  {
    "transactionId": 5,
    "portfolioId": 2,
    "portfolioName": "Conservative Fund",
    "stockId": 1,
    "stockSymbol": "AAPL",
    "stockName": "Apple Inc.",
    "transactionType": "BUY",
    "quantity": 2,
    "pricePerShare": 190.23,
    "totalAmount": 380.46,
    "transactionDate": "2025-07-25T19:59:46.250231",
    "fees": 2.50,
    "description": "BUY 2 shares of AAPL @ $190.23",
    "netAmount": 382.96
  }
]

=== POSITION VERIFICATION ===
All Positions (Current Holdings):
[
  {
    "positionId": 1,
    "portfolioId": 1,
    "portfolioName": "Growth Fund",
    "stockId": 1,
    "stockSymbol": "AAPL",
    "stockName": "Apple Inc.",
    "quantity": 10,
    "averageCost": 190.73,
    "totalCost": 1907.25,
    "currentValue": 1902.30,
    "updatedAt": "2025-07-25T19:59:46.24158",
    "summary": "10 shares of AAPL at avg cost $190.73",
    "gainLoss": -4.95,
    "gainLossPercentage": -0.2600
  },
  {
    "positionId": 2,
    "portfolioId": 1,
    "portfolioName": "Growth Fund",
    "stockId": 3,
    "stockSymbol": "MSFT",
    "stockName": "Microsoft Corp.",
    "quantity": 3,
    "averageCost": 310.40,
    "totalCost": 931.20,
    "currentValue": 930.00,
    "updatedAt": "2025-07-25T19:59:46.246765",
    "summary": "3 shares of MSFT at avg cost $310.40",
    "gainLoss": -1.20,
    "gainLossPercentage": -0.1300
  },
  {
    "positionId": 3,
    "portfolioId": 2,
    "portfolioName": "Conservative Fund",
    "stockId": 2,
    "stockSymbol": "GOOGL",
    "stockName": "Alphabet Inc.",
    "quantity": 5,
    "averageCost": 126.24,
    "totalCost": 631.20,
    "currentValue": 627.25,
    "updatedAt": "2025-07-25T19:59:46.249273",
    "summary": "5 shares of GOOGL at avg cost $126.24",
    "gainLoss": -3.95,
    "gainLossPercentage": -0.6300
  },
  {
    "positionId": 4,
    "portfolioId": 2,
    "portfolioName": "Conservative Fund",
    "stockId": 1,
    "stockSymbol": "AAPL",
    "stockName": "Apple Inc.",
    "quantity": 2,
    "averageCost": 191.48,
    "totalCost": 382.96,
    "currentValue": 380.46,
    "updatedAt": "2025-07-25T19:59:46.251714",
    "summary": "2 shares of AAPL at avg cost $191.48",
    "gainLoss": -2.50,
    "gainLossPercentage": -0.6500
  }
]

=== PORTFOLIO ANALYSIS ===
Portfolio Summary (High Level):
[
  {
    "portfolioID": 1,
    "name": "Growth Fund",
    "description": "Alice's test portfolio",
    "totalValue": 2832.30,
    "totalCost": 2838.45,
    "createdAt": "2025-07-25T19:59:46.234127",
    "updatedAt": "2025-07-25T19:59:46.247172",
    "user": {
      "id": 1,
      "username": "alice",
      "firstName": "Alice",
      "lastName": "Smith",
      "createdAt": "2025-07-25T19:59:46.226184",
      "active": true,
      "fullName": "Alice Smith"
    },
    "gainLoss": -6.15,
    "gainLossPercentage": -0.2200
  },
  {
    "portfolioID": 2,
    "name": "Conservative Fund",
    "description": "Bob's test portfolio",
    "totalValue": 1007.71,
    "totalCost": 1014.16,
    "createdAt": "2025-07-25T19:59:46.235113",
    "updatedAt": "2025-07-25T19:59:46.252314",
    "user": {
      "id": 2,
      "username": "bob",
      "firstName": "Bob",
      "lastName": "Johnson",
      "createdAt": "2025-07-25T19:59:46.228278",
      "active": true,
      "fullName": "Bob Johnson"
    },
    "gainLoss": -6.45,
    "gainLossPercentage": -0.6400
  }
]

=== STOCK DATA ===
All Stocks:
[
  {
    "stockID": 1,
    "symbol": "AAPL",
    "companyName": "Apple Inc.",
    "currentPrice": 190.23,
    "lastUpdated": "2025-07-25T19:59:46.231062",
    "sector": null,
    "marketCap": 0,
    "displayName": "AAPL - Apple Inc."
  },
  {
    "stockID": 2,
    "symbol": "GOOGL",
    "companyName": "Alphabet Inc.",
    "currentPrice": 125.45,
    "lastUpdated": "2025-07-25T19:59:46.232037",
    "sector": null,
    "marketCap": 0,
    "displayName": "GOOGL - Alphabet Inc."
  },
  {
    "stockID": 3,
    "symbol": "MSFT",
    "companyName": "Microsoft Corp.",
    "currentPrice": 310.00,
    "lastUpdated": "2025-07-25T19:59:46.232763",
    "sector": null,
    "marketCap": 0,
    "displayName": "MSFT - Microsoft Corp."
  }
]

=== PORTFOLIO TRANSACTION SUMMARIES ===
Portfolio 1 Transaction Summary:
{
  "totalTransactions": 3,
  "totalSellAmount": 620.00,
  "totalFees": 7.95,
  "sellTransactions": 1,
  "netInvested": 2832.30,
  "buyTransactions": 2,
  "totalBuyAmount": 3452.30
}

Portfolio 2 Transaction Summary:
{
  "totalTransactions": 2,
  "totalSellAmount": 0,
  "totalFees": 6.45,
  "sellTransactions": 0,
  "netInvested": 1007.71,
  "buyTransactions": 2,
  "totalBuyAmount": 1007.71
}

=== USER DATA ===
User 1 Details:
{
  "id": 1,
  "username": "alice",
  "firstName": "Alice",
  "lastName": "Smith",
  "createdAt": "2025-07-25T19:59:46.226184",
  "active": true,
  "fullName": "Alice Smith"
}

User 2 Details:
{
  "id": 2,
  "username": "bob",
  "firstName": "Bob",
  "lastName": "Johnson",
  "createdAt": "2025-07-25T19:59:46.228278",
  "active": true,
  "fullName": "Bob Johnson"
}

=== TRANSACTION VALIDATION ===
Planned Test Transactions:
1. Alice buys 10 AAPL @ 190.23 (fee: 4.95)
2. Alice buys 5 MSFT @ 310.00 (fee: 2.00)
3. Alice sells 2 MSFT @ 310.00 (fee: 1.00)
4. Bob buys 5 GOOGL @ 125.45 (fee: 3.95)
5. Bob buys 2 AAPL @ 190.23 (fee: 2.50)

Total Expected: 5 transactions across 2 portfolios
```

### File Structure:

![Current File Structure](/assets/img/files.png)

