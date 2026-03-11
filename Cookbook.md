## Breakfasts  🥞
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND #breakfast
SORT file.name asc
```

---

## Salads  🥗
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND #salad
SORT file.name asc
```

---

## Soups/Stews 🍲
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND (#soup OR #stew)
SORT file.name asc
```

## Vegetarian 🥕🍅🍄‍🟫🥦

```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND #vegetable
SORT file.name asc
```

---
## Fish 🐟
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND #fish
SORT file.name asc
```
## Meat 🥩
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND (#chicken or #meat)
SORT file.name asc
```
---
## Curry 🍛
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND (#curry)
SORT file.name asc
```

---
## Pasta 🍝
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND (#pasta)
SORT file.name asc
```
---

## Sauces/Dressings
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND (#dressing OR #sauce)
SORT file.name asc
```

## Baking 🍞 🎂
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe AND (#baking)
SORT file.name asc
```

## By Source
### Much More Veg
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe 
WHERE source = "Much More Veg"
SORT file.name asc
```

---
## All
```dataview
TABLE WITHOUT ID file.link as "Recipe", (choice(contains(tags, "new"), "🆕", "")) as "", (choice(contains(tags, "favourite"), "⭐", "")) as "⭐", (choice(contains(tags, "quick"), "🏃", "")) as "🏃", (choice(contains(tags, "vegetarian"), "🥕", "")) as "🥕", preptime as "🔪", (default(preptime, 0) + default(cooktime, 0)) as "⏳", source as "📖"
FROM #recipe
SORT file.name asc
```