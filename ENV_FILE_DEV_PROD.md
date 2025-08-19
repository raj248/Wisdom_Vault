For managing **different environment files** like `env.dev`, `env.prod`, etc., in React Native (Expo) or any React project, you have a few standard approaches. I’ll break it down clearly.

---

## 1. **Using `react-native-dotenv` or `react-native-config` (React Native / Expo)**

### Setup:

1. Install the package:

```bash
npm install react-native-dotenv
# or
yarn add react-native-dotenv
```

2. Create your `.env` files in the project root:

```
.env.dev
.env.prod
.env.staging
```

Example `.env.dev`:

```env
API_URL=https://dev.api.example.com
APP_NAME=MyApp (Dev)
```

Example `.env.prod`:

```env
API_URL=https://api.example.com
APP_NAME=MyApp
```

3. Configure Babel (`babel.config.js`) for Expo / React Native:

```js
module.exports = function(api) {
  api.cache(true);
  return {
    presets: ['babel-preset-expo'],
    plugins: [
      ["module:react-native-dotenv", {
        "moduleName": "@env",
        "path": ".env",
        "blocklist": null,
        "allowlist": null,
        "safe": false,
        "allowUndefined": true
      }]
    ]
  };
};
```

4. Use in your code:

```js
import { API_URL, APP_NAME } from '@env';

console.log(API_URL, APP_NAME);
```

5. **Switch env files on build** using scripts in `package.json`:

```json
"scripts": {
  "start:dev": "ENVFILE=.env.dev expo start",
  "start:prod": "ENVFILE=.env.prod expo start",
  "build:dev": "ENVFILE=.env.dev expo build:android",
  "build:prod": "ENVFILE=.env.prod expo build:android"
}
```

> **Note:** Expo CLI respects `ENVFILE` environment variable if using `react-native-dotenv`.

---

## 2. **Using `expo-constants` with `.env` + `app.config.js`**

Expo supports dynamic configuration at build time:

1. Install `dotenv`:

```bash
npm install dotenv
```

2. Create `.env` files:

```
.env.development
.env.production
```

3. In `app.config.js`:

```js
import 'dotenv/config';

export default ({ config }) => {
  const env = process.env.APP_ENV || 'development';

  return {
    ...config,
    extra: {
      API_URL: process.env.API_URL,
      APP_NAME: process.env.APP_NAME,
      ENV: env,
    },
  };
};
```

4. Run with different environment variables:

```bash
APP_ENV=development expo start
APP_ENV=production expo start
```

5. Access in code:

```js
import Constants from 'expo-constants';

console.log(Constants.manifest.extra.API_URL);
```

---

## 3. **For standard React (web) projects using Vite / CRA / Next.js**

### CRA:

* Use `.env.development`, `.env.production`, `.env.local` files.
* Prefix variables with `REACT_APP_`:

```
REACT_APP_API_URL=https://dev.api.example.com
```

* Access in code:

```js
console.log(process.env.REACT_APP_API_URL);
```

* CRA automatically loads the correct `.env` file based on `NODE_ENV` (`development` vs `production`).

---

### ✅ Key Tips:

* Never commit sensitive `.env` files to git (use `.env.example` as a template).
* Use scripts or CI/CD pipelines to set the proper `ENVFILE` or environment variables for each build.
* In Expo, `app.config.js` + `dotenv` is usually the cleanest way to have multiple environment files for dev, staging, and production.

---

If you want, I can write a **ready-to-use Expo setup** with `env.dev`, `env.staging`, `env.prod` that automatically picks the right `.env` file based on `yarn build:prod` vs `yarn build:dev`. It works without modifying every import.

Do you want me to do that?
