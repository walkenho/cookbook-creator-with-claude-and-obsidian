---
name: recipe
description: Format recipe data into a structured markdown file with YAML frontmatter, ingredients checklist, comments, and steps sections.
argument-hint: [recipe data, file path, or description]
---

Format the provided recipe data as a markdown file and save it.

## Input

The recipe data may arrive in any of these forms — handle all of them:

- **Pasted raw text** (e.g. copied from a website or book): parse it to extract the fields below.
- **Structured data** (JSON, YAML, or similar): read the fields directly.
- **File path**: read the file at that path first, then parse.
- **Interactive / incomplete input**: if critical fields are missing (title, ingredients, steps), ask the user to provide them before proceeding.

The recipe data is: $ARGUMENTS

## Output format

Save the recipe as a markdown file. Use the recipe title with appropriate title casing as filename, e.g. `Broccolini Soba Noodle Salad.md`. Save it in the current working directory unless the user specifies otherwise.

The file must follow this exact structure:

```
---
tags:
- recipe
- <category tag(s), e.g. breakfast, salad, soup, stew, vegetable, chicken, meat, fish, pasta, dessert>
- <vegetarian if vegetarian>
- new
serves: <number>
preptime: <number of minutes>
cooktime: <number of minutes>
source: <book or website name>
---

## Ingredients

- [ ] <ingredient 1>
- [ ] <ingredient 2>
…

## Comments

<Any notes, tips, or description about the dish. If none provided, omit this section entirely.>

## Steps

1. <Step 1>
2. <Step 2>

## Per Serving

* <number> kcal
* <number>g protein
* <number>g fat
* <number>g carbohydrates
…
```

## Rules

- ALWAYS stay true to the original data, nevert change the text, never make things up.
- Tags: always include `recipe`. Always include `new`. Include `vegetarian` if the dish is vegetarian. Infer category tags from the ingredients and dish type. Choose from: breakfast, salad, soup, stew, vegetable, chicken, meat, fish, pasta, dessert, dressing. Add dish tags like `high-protein`, `meal-prep` where appropriate. Only add tags that are clearly justified. 
- `serves`, `preptime`, `cooktime`: use integers.
- `preptime` is active preparation, cooktime is additional time cooking. If only one is provided, list it as `preptime`. If `preptime`/`cooktime` are not provided, omit the fields.
- `source`: use the book title, website name, or "Unknown" if not provided.
- Ingredients: use `- [ ]` checkboxes. Include quantities and units. 
- Steps: use a numbered list. Be clear and concise.
- Per Serving: Include kcal, protein and fat if present. If data is not present, omit this section.
- After saving the file, confirm the filename and path to the user.
