# Currency Converter

A lightweight, real-time currency converter built with **HTML, CSS and vanilla JavaScript**. Select a source and target currency, enter an amount, and get an instant conversion using live exchange rates.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [APIs & Resources Used](#apis--resources-used)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Features

- Live exchange rates fetched on page load and on every conversion
- 150+ currencies available in both dropdowns
- Country flag updates automatically when a currency is selected
- Defaults to **USD → INR** for a quick start
- Input validation: empty or invalid amounts fall back to `1`
- Clean, interactive UI with hover animations
- No frameworks, no build tools, no dependencies to install

## Tech Stack

| Layer      | Technology                         |
| ---------- | ---------------------------------- |
| Markup     | HTML5                              |
| Styling    | CSS3 (Flexbox, transitions)        |
| Logic      | JavaScript (ES6+, Fetch API, async/await) |
| Icons      | Font Awesome 6                     |

## Project Structure

```
currency-converter/
├── index.html      # Page markup
├── style.css       # Styles and animations
├── countries.js    # Currency code → country code mapping (for flags)
├── app.js          # Core logic: dropdowns, API calls, conversion
└── README.md
```

## Getting Started

No installation or build step is required.

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/currency-converter.git
   ```
2. **Open the project folder**
   ```bash
   cd currency-converter
   ```
3. **Run the app**
   Open `index.html` in any modern browser, or use a local server such as the VS Code *Live Server* extension.

> An active internet connection is required to fetch exchange rates and country flags.

## Usage

1. Enter the amount you want to convert.
2. Choose the **From** currency.
3. Choose the **To** currency.
4. Click **Get Exchange Rate** to see the converted value.

Example output:

```
1 USD = 83.25 INR
```

## How It Works

1. On load, `app.js` populates both dropdowns from the `countryList` object defined in `countries.js`.
2. When a currency is changed, the matching country flag is loaded from FlagsAPI.
3. On clicking the button, the app requests the rate file for the selected base currency:
   ```
   https://cdn.jsdelivr.net/npm/@fawazahmed0/currency-api@latest/v1/currencies/<from>.json
   ```
4. The target rate is read from the response and multiplied by the entered amount.
5. The result is rendered in the message box.

## APIs & Resources Used

- [Free Currency Exchange Rates API](https://github.com/fawazahmed0/exchange-api) by fawazahmed0 (served via jsDelivr)
- [FlagsAPI](https://flagsapi.com/) for country flag images
- [Font Awesome](https://fontawesome.com/) for icons

## Future Improvements

- Swap button to reverse the From/To currencies
- Error handling and a user-friendly message when the API is unreachable
- Rounding the result to 2 decimal places
- Mobile-first responsive layout improvements
- Dark mode
- Historical rates chart

## Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## License

This project is licensed under the [MIT License](LICENSE).

## Author

**Your Name**
GitHub: [@your-username](https://github.com/your-username)

---

If you found this project useful, consider giving it a ⭐
