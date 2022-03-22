# Origami Technical Excercise 

We would like you to use the [securities quotes api](#using-our-securities-quotes-api) (also known as stock prices) to populate a client-side component with their percentage change for the day. We do not expect any server-side code to be written for this exercise.

An example of how this component could look is below. However, it does not need to look exactly like this.
![Screenshot of an example securities data component](https://user-images.githubusercontent.com/51677/67555386-b6c5fc80-f700-11e9-86bd-55e975be0441.png)


- Please don't spend more than 1 hour on this exercise.
- We're not expecting you to complete this exercise, do only as much as you can within the time that you have.
- We are more interested in how you work than in how much code you write.
- You can use Google or any other resources you would like.
- We prefer to see solutions which use HTML, JavaScript and Sass/CSS, without using a framework like React or Vue.

## Prerequisites

Running this project requires [Node.js](https://nodejs.org/en/) 14.x and [npm](https://www.npmjs.com/).

## Getting started

1. Clone this repository (`Financial-Times/origami-tech-interview-exercise`) to your machine.
2. Install the dependencies with `npm install`.
3. Start the app with `npm run dev`.
4. Make changes by editing the HTML in `index.html`, the JavaScript in `src/index.js`, and the Sass in `src/index.scss`.

## Using our Securities Quotes API

To fetch the day's percentage change for a security you can use our Securities Quotes API, which is located at https://markets-data-api-proxy.ft.com/research/webservices/securities/v1/quotes.

The Securities Quotes API is a real production API and as such the values in the response will change over time.

Documentation for the Securities Quotes API is below.

### HTTP Request

`GET https://markets-data-api-proxy.ft.com/research/webservices/securities/v1/quotes`

### URL Query Parameters

| Parameter | Description |
|-----------|-------------|
| `symbols` | Any valid [symbol](Symbols) for a security, or a comma separated list of [symbols](Symbols), e.g. for the FTSE 100 use `FTSE:FSI`. For the FTSE 100 and S&P 500 use `FTSE:FSI,INX:IOM`.  |

### Symbols

We would like you to display the information from the following symbols (these are the securities we show on the [FT.com front page](https://www.ft.com) 📰).

| Security        | Symbol     |
|-----------------|------------|
| FTSE 100        | `FTSE:FSI` |
| S&P 500         | `INX:IOM`  |
| Euro/Dollar     | `EURUSD`   |
| Pound/Dollar    | `GBPUSD`   |
| Brent Crude Oil | `IB.1:IEU` |

### Example

#### Request
`GET https://markets-data-api-proxy.ft.com/research/webservices/securities/v1/quotes?symbols=FTSE:FSI,INX:IOM`

#### Response
```json
{
  "data": {
    "items": [
      {
        "symbolInput": "FTSE:FSI",
        "basic": {
          "symbol": "FTSE:FSI",
          "name": "FTSE 100 Index",
          "exchange": "FTSE International",
          "exhangeCode": "FSI",
          "bridgeExchangeCode": "GBFT",
          "currency": "GBP"
        },
        "quote": {
          "lastPrice": 7058.8600000000006,
          "openPrice": 7169.32,
          "high": 7169.32,
          "low": 6993.06,
          "previousClosePrice": 7169.32,
          "change1Day": -110.45999999999913,
          "change1DayPercent": -1.5407318964699459,
          "change1Week": -134.36999999999898,
          "change1WeekPercent": -1.8680064449489171,
          "timeStamp": "2021-08-19T15:35:30",
          "volume": 602903871.0
        }
      },
      {
        "symbolInput": "INX:IOM",
        "basic": {
          "symbol": "INX:IOM",
          "name": "S&P 500 INDEX",
          "exchange": "CME:Index and Options Market",
          "exhangeCode": "IOM",
          "bridgeExchangeCode": "USCO",
          "currency": "USD"
        },
        "quote": {
          "lastPrice": 4412.2300000000005,
          "openPrice": 4382.4400000000005,
          "high": 4418.61,
          "low": 4367.7300000000005,
          "closePrice": 4400.27,
          "previousClosePrice": 4400.27,
          "change1Day": 11.960000000000036,
          "change1DayPercent": 0.27180150308958395,
          "change1Week": -48.599999999999454,
          "change1WeekPercent": -1.0894833472694421,
          "ask": 4413.55,
          "bid": 4411.68,
          "timeStamp": "2021-08-19T16:11:17",
          "volume": 986981000.0
        }
      }
    ]
  },
  "timeGenerated": "2021-08-19T16:21:17"
}
```
