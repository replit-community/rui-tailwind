# Tailwind Config

Bring RUI values to Tailwind

## Usage

Follow the [installation process](https://tailwindcss.com/docs/guides/vite) to add Tailwind to your project.

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

I used Vite, but the same principles should apply to any framework - just copy over what you need.

1. Copy `tailwind.config.js` to your root directory
2. Include `styles/global.css` (global resets)
3. Include `styles/tokens.css` (actual token values)
4. Include `rui/tokens.js` if necessary (autocomplete for token values in JS)

If you're not seeing any styles, modify make sure you're targetting everything correctly in `tailwind.config.js` (I do provide a set of sensible defaults though). If you would like to **keep** the old Tailwind values, you can "extend" the existing Tailwind config instead.

```js
// current - overrides existing Tailwind classes
{
    theme: {
        fontFamily: { ... }
    }
}

// new - extends existing Tailwind classes
{
    theme: {
        extend: {
            fontFamily: { ... }
        }
    }
}
```

## Caveats

**You need an extension.**

The "[Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)" extension is a necessity when working with Tailwind. It automatically adjusts to work with the existing Tailwind config. Unless you're super comfortable with Tailwind and know how each modification actually affects the class names, I would highly recommend working in VS Code until a Replit extension can provide a similar workflow.

**Questionable support.**

I'm not 100% sure if [arbitrary value support](https://v2.tailwindcss.com/docs/just-in-time-mode) works for all classes because of my modifications, but explicitly setting the styles works well enough for my use cases.
