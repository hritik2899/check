# Observer Design Pattern - Combined Example

## Overview
The Observer design pattern is a behavioral design pattern in which an object, known as the **Publisher**, maintains a list of dependents, called **Subscribers**, and notifies them of any state changes, usually by calling one of their methods.

This README provides two real-world examples of the Observer design pattern presented in a combined tree structure format.

## Combined Tree Structure

```plaintext
Observer Design Pattern

  |-- Stock Market Ticker System
  |   |-- **Publisher**: `StockMarketDataSource`
  |   |   |-- **Attributes**:
  |   |   |   |-- `subscribers[]`: List of Subscriber objects
  |   |   |   |-- `stockPrices`: Current stock prices
  |   |   |
  |   |   |-- **Methods**:
  |   |       |-- `subscribe(subscriber: Subscriber)`
  |   |       |-- `unsubscribe(subscriber: Subscriber)`
  |   |       |-- `notifySubscribers()`
  |   |       |-- `updateStockPrice(newPrice: float)`
  |   |
  |   |-- **Workflow**:
  |       |-- 1. `updateStockPrice(newPrice):`
  |       |     |-- Update `stockPrices`
  |       |     |-- `notifySubscribers()`
  |       |
  |       |-- 2. `notifySubscribers():`
  |             |-- foreach(`subscriber` in `subscribers[]`):
  |             |     |-- `subscriber.update(stockPrices)`
  |
  |-- **Subscriber Interface**
      |-- **Methods**:
          |-- `update(stockPrices: float)`
      |
  |-- **Concrete Subscribers**:
      |-- `UserInterfaceComponent1`
      |-- `UserInterfaceComponent2`
      ...

------------------------------------------------------

  |-- Email Notification System
  |   |-- **Publisher**: `BlogNewsletterSystem`
  |   |   |-- **Attributes**:
  |   |   |   |-- `subscribers[]`: List of Subscriber objects
  |   |   |   |-- `latestPost`: Latest blog post
  |   |   |
  |   |   |-- **Methods**:
  |   |       |-- `subscribe(subscriber: Subscriber)`
  |   |       |-- `unsubscribe(subscriber: Subscriber)`
  |   |       |-- `notifySubscribers()`
  |   |       |-- `publishNewPost(post: string)`
  |   |
  |   |-- **Workflow**:
  |       |-- 1. `publishNewPost(post):`
  |       |     |-- Update `latestPost`
  |       |     |-- `notifySubscribers()`
  |       |
  |       |-- 2. `notifySubscribers():`
  |             |-- foreach(`subscriber` in `subscribers[]`):
  |             |     |-- `subscriber.update(latestPost)`
  |
  |-- **Subscriber Interface**
      |-- **Methods**:
          |-- `update(latestPost: string)`
      |
  |-- **Concrete Subscribers**:
      |-- `UserEmailService1`
      |-- `UserEmailService2`
      ...
