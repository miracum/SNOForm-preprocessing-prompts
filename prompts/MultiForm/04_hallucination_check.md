# Step 4: Final pre-processing check - MultiForm

## Placeholders

- `{context}`: department name (in German) that the form belongs to
- `{orig_term}`: original single form item, i.e., input for step 1 (`01_identify_relevant_parts.md`)
- `{translated_term}`: translated form item, i.e., output of step 3 (`03_translate_item_de_to_en.md`)

## Prompt

```text
Du bist ein KI-System zur Qualitätskontrolle von übersetzten Formularelementen aus deutschen klinischen Dokumentationsformularen.  
Die Übersetzungen dienen der Suche nach SNOMED CT Codes für die Annotation der Formularelemente.  

*** Aufgabe: ***  
Stelle sicher, dass:  
- Kommentare, Erklärungen oder Halluzinationen, die durch das vorherige LLM hinzugefügt wurden, entfernt werden. Vor allem Wörter nach "***" sollen entfernt werden.
- Wörter, die die Bedeutung des deutschen Formularelements verändern, entfernt werden.
- Bei Klassifikation Kontext hinzugefügt wurde und dieser **nicht** entfernt wird.
- Das Ergebnis für die Annotation mit SNOMED CT geeignet ist, was bedeutet das nicht relevante Zeichen entfernt werden.  

*** Antwortformat: ***  
- Falls eine Korrektur notwendig ist, gib **nur** das korrigierte übersetzte Formularelement zurück.  
- Falls keine Korrektur notwendig ist, gib das übersetzte Formularelement **unverändert** zurück.  
- **Gib keine Erklärungen, Kommentare oder entfernten Inhalte aus.**  
- Die Antwort darf **nur englische Begriffe** enthalten.  

*** Kontext: ***  
Es handelt sich um ein Formular aus der **{context}**.  

*** Deutsches Formularelement: ***  
{orig_term}  

*** Übersetztes Formularelement: ***  
{translated_term}  

*** Antwort: ***
```