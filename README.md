# OpenKit

Free everyday tools that run entirely in your browser. No sign-up, no uploads, no tracking.

OpenKit is a single static page (`index.html`) with 35 tools. There is no build step and no dependencies.

## Tools

- **Text:** word counter, case converter, duplicate line remover, Lorem Ipsum generator
- **Developer:** JSON formatter and validator, Base64, URL encoder, UUID generator, JWT decoder, regex tester
- **Calculators:** percentage, BMI, EMI, compound interest, age, date difference, discount
- **Converters:** length, weight, temperature, data storage
- **Security:** password generator, password strength checker, hash generator, random numbers
- **Color:** HEX and RGB converter, contrast checker
- **Data:** CSV to JSON, JSON to CSV
- **Miscellaneous:** number base converter, number to words
- **Student:** attendance calculator, GPA calculator
- **Productivity:** stopwatch, countdown timer

Features: search, category filters, favorites, recently used tools, light and dark themes, mobile-friendly layout. Preferences are saved in your browser's localStorage.

## Run locally

Open `index.html` in any modern browser. Or serve the folder:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000. The hash generator needs a secure context, which `localhost` and `https` both provide.

## Upload to GitHub

1. On github.com, choose **New repository**, name it `OpenKit`, and create it.
2. Choose **Add file → Upload files**, drag in every file from this folder, and commit.

## Deploy

**GitHub Pages:** open **Settings → Pages**, set the source to the `main` branch and the `/ (root)` folder, then save. The site goes live at `https://<your-username>.github.io/OpenKit/`.

**Vercel:** import the repository at vercel.com/new. Leave the framework preset as **Other** and the build command empty. Deploy.

## Add a tool

Tools are defined in the `<script>` block of `index.html` with one `add(...)` call:

```js
add('my-tool', 'My tool', 'Category', 'One-line description.',
  [F('t', 'Input', 'a', 'default text')],      // fields: key, label, type, default
  v => v.t.toUpperCase());                      // return a string, or throw Error('message')
```

Field types: `a` textarea, `t` text, `n` number, `d` date, `k` color, `p` password, `c` checkbox, `s` select (pass the options array last).

## License

MIT. See [LICENSE](LICENSE).
