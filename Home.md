---
current_year: "1986"
---

## Characters
```dataviewjs
dv.table(
	["Name", "Birth Year", "Age", "Height"],
	dv.pages("#character")
		.map((b) => {
		    const age = b.birth_year
			    ? +dv.page("Home").current_year - +b.birth_year
			    : null;
			return [b.file.link, b.birth_year ?? "\\-", age ?? "\\-", b.height ?? "\\-"];
		})
)
// TABLE WITHOUT ID link(file.link, name) AS "Name", birth_year as "Birth Year", height AS "Height" FROM #character
```

## Dates
```dataview
TABLE WITHOUT ID link(file.link, string(file.day)) AS "Date" FROM #date
```

## Places
```dataview
TABLE WITHOUT ID link(file.link, name) AS "Place" FROM #location
```
