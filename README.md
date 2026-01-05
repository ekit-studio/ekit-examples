# Ekit – Template Example (SSR)

This template is an example of a **Server-Side Rendered (SSR)** website built with **Ekit**.  
It demonstrates the use of **layouts**, **partials**, **datasources**, **multilingual content**, and list/detail navigation.

The i18n files (`fr`, `en`) are already included in this template.

---

## Project Setup (Required)

Before using this template, you must create a **new multilingual project**.

1. In Ekit, create a **new project**
2. Enable the following languages:
   - **French (`fr`)**
   - **English (`en`)**

This template relies on a multilingual project configuration.

---

## Template Installation

1. Open your **project** in Ekit
2. Go to **Templates**
3. Create a **new template**
4. Copy the files from this template example  
   **or** replace the content of the existing files with the provided ones

Once the files are in place, configure the tables described below.

---

## Tables to Create

All tables must be created from within your **project**, in the **Tables** section.

### `home-features`

This table is used to display the main features on the homepage.

| Field | Type | Multilingual |
|------|------|-------------|
| Title | text | Yes |
| Description | longtext | Yes |

👉 Create **3 records** in this table.

Make sure the content language is set to English before entering the data below.

| id | title                         | description                                                                 |
|----|-------------------------------|-----------------------------------------------------------------------------|
| 1  | Intelligent Automation        | Automate repetitive tasks using AI and save valuable time every day.       |
| 2  | Advanced Data Analysis        | Analyze, understand, and leverage your textual data with powerful NLP tools. |
| 3  | Easy and Fast Integration     | Easily integrate the solution into your existing tools using modern APIs.  |

---

### `home-process`

This table describes the steps or process behind the site or product.

| Field | Type | Multilingual |
|------|------|-------------|
| Title | text | Yes |
| Description | longtext | Yes |

👉 Create **3 records** in this table.

Make sure the content language is set to English before entering the data below.

| id | title                     | description                                                                 |
|----|---------------------------|-----------------------------------------------------------------------------|
| 1  | Collect Data              | Gather data from your sources, documents, or user inputs in a structured way. |
| 2  | Process & Understand      | Use NLP and AI models to analyze, structure, and extract meaningful insights. |
| 3  | Deliver Insights          | Transform processed data into clear answers, summaries, or actionable outputs. |


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

Make sure the content language is set to English before entering the data below.

| id | name           | role        | description                                  | overview                                                                                                                                                                                                 | tag    | email                   |
|----|----------------|-------------|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|-------------------------|
| 1  | Henry Walker   | Developer   | Senior full-stack developer specialized in AI applications. | <h3>Profile</h3><p>Henry is a <strong>senior full-stack developer</strong> with a strong background in AI-powered applications.</p><ul><li>10+ years of experience</li><li>Expert in JavaScript & Node.js</li><li>AI & NLP integrations</li></ul> | Core   | henry@example.com       |
| 2  | Sarah Collins  | Product Manager | Product leader focused on user-centered design. | <h3>About</h3><p>Sarah leads product strategy with a focus on <em>usability</em> and business impact.</p><ul><li>Roadmap planning</li><li>Stakeholder alignment</li><li>User research</li></ul><p><strong>Mission:</strong> Build products users love.</p> | Team   | sarah@example.com       |
| 3  | Michael Brown  | AI Engineer | Expert in machine learning and NLP systems. | <h3>Expertise</h3><p>Michael specializes in <strong>machine learning</strong> and <strong>NLP pipelines</strong>.</p><ul><li>Text embeddings</li><li>Semantic search</li><li>Summarization</li></ul> | Expert | michael@example.com     |
| 4  | Laura Martinez | UX Designer | UX/UI designer focused on clarity and usability. | <h3>Design Philosophy</h3><p>Laura believes in <em>simple, accessible, and elegant</em> interfaces.</p><ul><li>User journeys</li><li>Design systems</li><li>Prototyping</li></ul><p><strong>Goal:</strong> Reduce friction and increase clarity.</p> | Team   | laura@example.com       |
| 5  | David Nguyen   | DevOps Engineer | Infrastructure and deployment specialist. | <h3>Responsibilities</h3><p>David ensures <strong>reliability and scalability</strong> of the platform.</p><ul><li>CI/CD pipelines</li><li>Cloud infrastructure</li><li>Monitoring & security</li></ul><p><em>Always on, always secure.</em></p> | Core   | david@example.com       |



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
