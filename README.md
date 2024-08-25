https://icones.js.org/collection/mdi
https://www.npmjs.com/package/@pinia/nuxt
https://prazdevs.github.io/pinia-plugin-persistedstate/frameworks/nuxt-3.html
https://medium.com/techvblogs/spa-authentication-using-laravel-9-sanctum-vue-3-and-vite-b1fb1020d754
https://icones.js.org/


for icon 

npx nuxi module add icon
npm i -D @iconify-json/mdi

pinia next 
npm i @pinia/nuxt


for pinia persistedstate 
pm i -D @pinia-plugin-persistedstate/nuxt
npm i pinia -f

  build: {
    transpile: ['pinia-plugin-persistedstate'],
  },
  

AUTH / BACKEND (for install select api)
composer require laravel/breeze --dev
php artisan breeze:install 

App\Models\User::create(["name"=> "John Weeks Dev","email"=>"john@m.com","password"=>bcrypt("123123123")]);

# Nuxt 3 Minimal Starter

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Setup

Make sure to install the dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev

# pnpm
pnpm run dev

# yarn
yarn dev

# bun
bun run dev
```

## Production

Build the application for production:

```bash
# npm
npm run build

# pnpm
pnpm run build

# yarn
yarn build

# bun
bun run build
```

Locally preview production build:

```bash
# npm
npm run preview

# pnpm
pnpm run preview

# yarn
yarn preview

# bun
bun run preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.
# tiktok-app
