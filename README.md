Stock Market Ticker System
StockTickerService (Subject)
│
├── ClientApp1 (Observer)
│   └── Method: refresh()
│       └── Updates stock price display when StockTickerService changes price.
│
├── ClientApp2 (Observer)
│   └── Method: refresh()
│       └── Updates stock price display when StockTickerService changes price.
│
└── ClientApp3 (Observer)
    └── Method: refresh()
        └── Updates stock price display when StockTickerService changes price.

UpdatePrice() (Event)
└── Notifies all ClientApps to refresh their stock price displays.
News Feed Subscription System

NewsFeedService (Subject)
│
├── Subscriber1 (Observer)
│   └── Method: receive_update()
│       └── Receives new article notifications from NewsFeedService.
│
├── Subscriber2 (Observer)
│   └── Method: receive_update()
│       └── Receives new article notifications from NewsFeedService.
│
└── Subscriber3 (Observer)
    └── Method: receive_update()
        └── Receives new article notifications from NewsFeedService.

PublishArticle() (Event)
└── Triggers receive_update() method for all subscribers.
