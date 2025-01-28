
# useCurrencyInfo Hook

A simple and reusable React custom hook to fetch and display currency information using the [Free Currency Exchange Rates API](https://github.com/fawazahmed0/currency-api).

## Features

- Fetches real-time currency information for a given currency code.
- Lightweight and easy to use in any React project.
- Uses React's `useState` and `useEffect` for data fetching and state management.

## Installation

1. Clone this repository:
   ```bash
   git clone <repository-url>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start your React application:
   ```bash
   npm start
   ```

## Usage

To use the `useCurrencyInfo` hook in your React project:

1. Import the hook into your component:
   ```javascript
   import useCurrencyInfo from './path/to/useCurrencyInfo';
   ```

2. Call the hook with the desired currency code:
   ```javascript
   function App() {
       const currencyData = useCurrencyInfo('usd'); // Replace 'usd' with your desired currency code.

       return (
           <div>
               <h1>Currency Information</h1>
               <p>Base Currency: {currencyData?.usd || 'Loading...'}</p>
           </div>
       );
   }

   export default App;
   ```

## API Details

This hook fetches data from the [Currency API](https://github.com/fawazahmed0/currency-api) using the following endpoint structure:

```
https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/{currencyCode}.json
```

### Example Request

To fetch details for the USD currency:
```
https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/usd.json
```

### Example Response
```json
{
    "usd": {
        "eur": 0.9,
        "inr": 73.5,
        ...
    }
}
```

## Hook Parameters

| Parameter   | Type     | Description                                                                 |
|-------------|----------|-----------------------------------------------------------------------------|
| `currency`  | `string` | The currency code (e.g., `usd`, `inr`, `eur`) for which you want the data. |

## Hook Return Value

The hook returns a state object containing the fetched currency data. If the currency code is invalid or the data is still loading, it will return an empty object.

## Example Output

When using `useCurrencyInfo('usd')`, the returned `currencyData` object may look like this:

```json
{
    "eur": 0.9,
    "inr": 73.5,
    "btc": 0.000037
}
```

