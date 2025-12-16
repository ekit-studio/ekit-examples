# Ekit – Template Example (SSR)

This template is an example of a **Server-Side Rendered (SSR)** website built with **Ekit**.  
It demonstrates the use of **layouts**, **partials**, **datasources**, **multilingual content**, and list/detail navigation.

The i18n files (`fr`, `en`) are already included in this template.

---

## Template Installation

1. Create a new template in the **Ekit Studio**
2. Copy the files from this template example  
   **or** replace the content of the existing files with the provided ones

Once the files are in place, configure the tables described below.

---

## Tables to Create

### `home-features`

This table is used to display the main features on the homepage.

| Field | Type | Multilingual |
|------|------|-------------|
| Title | text | Yes |
| Description | longtext | Yes |

👉 Create **3 records** in this table.

---

### `home-process`

This table describes the steps or process behind the site or product.

| Field | Type | Multilingual |
|------|------|-------------|
| Title | text | Yes |
| Description | longtext | Yes |

👉 Create **3 records** in this table.

---

### `directory`

This table powers the directory list and detail pages.

| Field | Type | Multilingual |
|------|------|-------------|
| Name | longtext | No |
| Role | text | Yes |
| Description | longtext | Yes |
| Overview | richtext | Yes |
| Tag | text | Yes |
| Email | email | No |

👉 Create multiple records, for example:

- **Name**: Henry  
- **Role**: Developer  
- **Description**: Henry is the best developer  
- **Overview**: Rich description (WYSIWYG content)  
- **Tag**: Team / Core / Expert  
- **Email**: henry@example.com  

---

## Page Structure

### Directory Page (List)
- Datasource: `directory`
- Card-based layout
- Navigation to the detail page

### Directory Detail Page
- Datasource: `directory`
- Loaded using a `uid` query parameter
- Uses the `single` helper
- Automatic fallback when fields are empty

---

## Internationalization (i18n)

The template includes multilingual support out of the box.

Translations are accessed using the helper:

```hbs
{{ektrans "key.name"}}
```

No additional configuration is required.

---

## Helpers Used

- `ekdata` — access structured data
- `ektrans` — i18n translations
- `single` — fetch a single record
- `year` — current year

---

## Styling (Tailwind CSS)

This template includes a **precompiled Tailwind CSS file**, located at:

```
assets/css/tailwind.css
```

The template works immediately without any build step.

---

### Regenerating Tailwind CSS (optional)

If you modify Tailwind classes in the templates, you can regenerate the CSS.

#### 1. Install dependencies
```bash
npm install
```

#### 2. Compile Tailwind
```bash
npx tailwindcss -i ./assets/css/input.css -o ./assets/css/tailwind.css --minify
```

---

### Tailwind Configuration

Make sure your `tailwind.config.js` scans the Ekit template folders:

```js
module.exports = {
  content: [
    './views/**/*.hbs',
    './layouts/**/*.hbs',
    './partials/**/*.hbs',
    './components/**/*.hbs'
  ],
  theme: {
    extend: {}
  },
  plugins: []
}
```

---

## SSR Rendering

The site is fully rendered server-side by Ekit:
- fast
- SEO-friendly
- no mandatory client-side JavaScript

---

## Template Purpose

This template serves as:
- a demonstration of Ekit capabilities
- a base for building dynamic SSR websites
- a starting point for your own templates

---

© {{year}} — Generated with Ekit
