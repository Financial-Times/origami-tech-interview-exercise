# Origami Technical Interview

Use the [securities quotes api](#using-our-securities-quotes-api) (also known as stock prices) to populate a client-side component with their percentage change for the day.

Then, implement an interface to allow the user to set a preference whether to show stock prices as a percentage change for the day or for the week. Update the stocks component when the user makes a selection.

It could look something like the following.
![Screenshot of an example securities data component](https://user-images.githubusercontent.com/10405691/129941699-afd8964c-2135-4dd7-b7cc-0623beda2798.png)

We are more interested in how you work than in how much code you write. Treat this like a pair programming session, we are here to help so ask us questions and let us know what you are doing and why. You can use Google or any other resources you would like.

We're not expecting you to complete this exercise, do only as much as you can within the time that we have.

## Getting started

1. Clone the exercise with `git clone git@github.com:Financial-Times/next-tech-interview-exercise.git`.
2. Install the dependencies with `npm install`.
3. Start the app with `npm dev`.
4. To make changes see `index.html`, `src/index.js`, and `src/index.scss`.

## Using our Securities Quotes API

To fetch the day's percentage change for a security you can use our Securities Quotes API.

**HTTP Request**

`GET https://markets-data-api-proxy.ft.com/research/webservices/securities/v1/quotes`

**URL Query Parameters**

| Parameter | Description |
|-----------|-------------|
| `symbols` | Any valid symbol for a security, e.g. for the FTSE 100 use `FTSE:FSI`. |

**Symbols**

We would like you to display the information from the following symbols (these are the securities we show on the [FT.com front page](https://www.ft.com) 📰).

| Security        | Symbol     |
|-----------------|------------|
| FTSE 100        | `FTSE:FSI` |
| S&P 500         | `INX:IOM`  |
| Euro/Dollar     | `EURUSD`   |
| Pound/Dollar    | `GBPUSD`   |
| Brent Crude Oil | `IB.1:IEU` |
