# React Phone Catalog

A React + TypeScript phone catalog application built with Vite. The app includes product browsing, catalog filtering, cart management, and favorites persistence.

## Key Features

- Product catalog for phones, tablets, and accessories
- Category-based routing with React Router v6
- Product detail pages with image gallery, color/capacity switching, and recommended products
- Shopping cart and favorites using React Context
- Local storage persistence for cart and favorites
- Static product data stored in JSON files under `public/api`
- Responsive layout and SCSS-based styling

## Tech Stack

- React 18
- TypeScript
- Vite
- SCSS
- React Router v6
- Context API
- LocalStorage

## Project Structure

### Root files

- `package.json` - project dependencies and scripts
- `tsconfig.json` - TypeScript configuration
- `vite.config.ts` - Vite configuration
- `index.html` - app entry HTML
- `README.md` - project documentation

### `public/`

- `public/api/` - static JSON data for products, phones, tablets, accessories, and product metadata
- `public/fonts/` - custom font assets
- `public/img/` - shared image assets used in UI and page layouts
- `public/_old/` - legacy/static backup copies of older API and image structures

### `src/`

- `src/index.tsx` - app entry point
- `src/App.tsx` - main application router and shared layout
- `src/App.scss` - global application styles
- `src/styles/grid.scss` - grid layout utilities
- `src/fonts.scss` - font imports and font-face definitions

### `src/components/`

Organized by feature and page:

- `CartPage/` - cart page implementation and styles
- `Catalog/` - catalog page, list, filters, and pagination
- `Favorites/` - favorites page and related UI
- `Footer/` - footer component
- `Header/` - header and mobile menu
- `HomePage/` - home page sections and brand landing content
- `NotFoundPage/` - 404 page
- `ProductCard/` - reusable product card component
- `ProductPage/` - detailed product page with gallery, specs, and actions

### `src/context/`

- `CartContext.tsx` - cart state, actions, totals, and localStorage persistence
- `FavoritesContext.tsx` - favorites state, toggle action, and localStorage persistence

### `src/types/`

Type definitions used across the application:

- `Cart.ts`
- `cartItem.ts`
- `CartProduct.ts`
- `FavoriteProduct.ts`
- `PhoneFull.ts`
- `PhoneShort.ts`
- `ProductBase.ts`

### `src/utils/`

- `mapToProductBase.ts` - helper for converting raw product data to `ProductBase` format for cards and favorites

## Routing

Defined in `src/App.tsx`:

- `/` - `HomePage`
- `/phones` - `Catalog` filtered to phones
- `/tablets` - `Catalog` filtered to tablets
- `/accessories` - `Catalog` filtered to accessories
- `/phones/:itemId` - `ProductPage`
- `/tablets/:itemId` - `ProductPage`
- `/accessories/:itemId` - `ProductPage`
- `/cart` - `CartPage`
- `/favorites` - `Favorites`
- `*` - `NotFoundPage`

## Data Sources

Static product data is imported from JSON files in `public/api`:

- `products.json` - product base data used by the catalog
- `phones.json`, `tablets.json`, `accessories.json` - full product details used by `ProductPage`

Images and media referenced by products are stored under `public/img/phones/`, `public/img/tablets/`, and `public/img/accessories/`.

## Scripts

- `npm install` - install dependencies
- `npm start` - start the development server
- `npm run build` - build the production app
- `npm run lint` - run JS/CSS linting and formatting
- `npm run format` - format TypeScript files with Prettier
- `npm run style-format` - format SCSS files with Stylelint
- `npm run deploy` - build and deploy using `mate-scripts`

## Notes

- Cart and favorites are stored in browser local storage under `cart` and `favourites`
- The catalog supports sorting, pagination, and page size controls via query parameters
- Product pages support variant switching by color and capacity
- The existing `homepage` setting in `package.json` is set to `.` for relative deployment paths
