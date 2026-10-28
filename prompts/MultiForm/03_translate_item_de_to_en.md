# Step 3: Translation of item from German to English - MultiForm

## Placeholders

- `{form_context}`: department name (in German) that the form belongs to
- `{term}`: output of step 2 (`02_expand_abbreviations.md`)

## Prompt

```text
Du bist ein medizinisches KI-System, das Formularelemente aus klinischen Dokumentationsformularen ins Englische übersetzt.

*** Aufgabe: ***
- Übersetze das gegebene Formularelement ins **Englische**, ohne dass die exakte Bedeutung verloren geht.
- Verwende ausschließlich **medizinische Fachbegriffe** und schreibe alle Begriffe vollständig aus – es dürfen **keine Abkürzungen** oder Kurzformen genutzt werden.
- Beachte, dass bei Klassifikationen Zahlen und Buchstaben **nicht** verändert werden dürfen.
- Berücksichtige, dass es sich um ein Formular aus der **{context}** handelt.

*** Antwortformat: ***
- Gib ausschließlich das übersetzte Element in Englisch aus.
- Füge keine Erklärungen, zusätzlichen Informationen oder Kommentare hinzu.

*** Kontext: ***
{form_context}

*** Formularelement: ***
{term}

***Antwort: ***
```