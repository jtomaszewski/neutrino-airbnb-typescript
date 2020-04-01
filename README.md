# Neutrino Typescript ESLint

Provides typescript integration with ESLint for neutrino React projects using Airbnb's ESLint config, following the Airbnb styleguide.

## Installation

This package is intended for use with [neutrino-typescript](https://github.com/davidje13/neutrino-typescript#readme),
so you should already have those installed and configured.

Note: Do not use `@neutrino/airbnb`. This preset will include airbnb preset on its' own.

1. Install dependencies:

   ```bash
   npm install --save-dev git+https://github.com/jtomaszewski/neutrino-airbnb-typescript
   ```

2. Include in `.neutrinorc.js`:

   ```javascript
   const airbnbTypescript = require('neutrino-airbnb-typescript');
   // ...

   module.exports = {
     use: [
       typescript(), // must be first in use section
       airbnbTypescript(), // order does not matter; can be later
       eslint(), // or any other eslint-based module
       node(), // or whichever target you are using
     ],
   };
   ```

3. Include type checking in `package.json` scripts:

   ```json
   {
     "scripts": {
       "lint": "eslint --format codeframe --ext mjs,jsx,js,tsx,ts src test && tsc"
     }
   },
   ```
