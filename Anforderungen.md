# KI AG - Retrieval Augmented Generation (RAG) Projekt

## User Story

**Als** Schüler der KI AG **möchte ich** ein RAG-System (Retrieval Augmented Generation) erstellen, **damit ich** verstehe, wie ein LLM mit externen Datenquellen (Webseiten und Dokumente) verbunden werden kann, um kontextbezogene Antworten zu liefern.

---

## Projektübersicht

In diesem Projekt lernt ihr, wie man ein lokales LLM mit externen Datenquellen verbindet. Das System kann dann Fragen zu Inhalten beantworten, die es ursprünglich nicht "kennt".

**Was ist RAG?**  
RAG (Retrieval Augmented Generation) ist eine Technik, bei der ein LLM mit einer Wissensdatenbank verbunden wird. Anstatt nur auf das trainierte Wissen zurückzugreifen, kann das Modell relevante Informationen aus Dokumenten abrufen und in seine Antworten einbeziehen.

---

## Aufgaben

### Phase 1: RAG für Website (Hauptaufgabe)

**Ziel:** Ein RAG-System erstellen, das Informationen von einer Website abrufen und Fragen dazu beantworten kann.

**Datenquelle:**  
https://herbartgymnasium.de/2025/11/23/forschen-staunen-entdecken-erste-mint-nacht-am-hgo/

**Schritte:**
1. Embedding-Modell initialisieren (`embeddinggemma:300m`)
2. Vektordatenbank einrichten
3. Website laden und Text extrahieren
4. Text in Chunks aufteilen
5. Chunks in Vektordatenbank speichern
6. RAG-Abfrage implementieren

**Erfolgskriterium:**  
Das LLM soll korrekt die **5 Abenteuerräume** erkennen und ausgeben, die im Beitrag genannt werden.

---

### Phase 2: RAG für PDF erweitern (Bonusaufgabe)

**Ziel:** Das bestehende RAG-System um PDF-Dokumente erweitern.

**Datenquelle:**  
Satzung vom Förderverein HGO (`data/Förderverein_HGO_Satzung.pdf`)

**Schritte:**
1. PDF laden und Text extrahieren
2. Text in Chunks aufteilen
3. Chunks in Vektordatenbank speichern
4. RAG-Abfrage für PDF implementieren

**Erfolgskriterium:**  
Das LLM soll korrekt den **Namen des Vereins** und seinen **Sitz** erkennen.

---

### Phase 3: Streamlit Oberfläche (Erweiterung)

**Ziel:** Eine benutzerfreundliche Web-Oberfläche für das RAG-System erstellen.

**Schritte:**
1. Streamlit installieren und einrichten
2. Chat-Interface erstellen
3. Auswahl zwischen Website und PDF ermöglichen
4. Antworten ansprechend darstellen

---

## Voraussetzungen & Setup

### Software installieren

| Software | Download-Link |
|----------|---------------|
| Python | https://www.python.org/downloads/ |
| VS Code | https://code.visualstudio.com/download |
| Ollama | https://ollama.com/download/windows |

### VS Code Erweiterungen einrichten

- **Python** - Python-Unterstützung
- **Pylance** - Intelligente Code-Vervollständigung
- **Jupyter** - Notebook-Unterstützung
- **Prettier** - Code-Formatierung

### Ollama Setup

1. Account bei Ollama erstellen
2. LLM herunterladen:
   ```bash
   # LLM für Text-Generierung (geringste stündliche/wöchentliche Nutzung)
   ollama pull gpt-oss:20b-cloud
   ```
3. Embedding-Modell herunterladen:
   ```bash
   # Embedding-Modell für Vektorisierung
   ollama pull embeddinggemma:300m
   ```

### Python-Pakete installieren

```bash
pip install -r requirements.txt
```

---

## Ressourcen & Dokumentation

| Thema | Link |
|-------|------|
| LangChain RAG Tutorial | https://docs.langchain.com/oss/python/langchain/rag |
| Embedding-Modell Docs | https://ollama.com/library/embeddinggemma:300m |
| LLM Docs | https://ollama.com/library/gpt-oss:20b-cloud |
| LangChain Ollama Integration | https://reference.langchain.com/python/integrations/langchain_ollama/#langchain_ollama.OllamaEmbeddings |

---

## Projektstruktur

```
KI AG/
├── rag.ipynb              # Arbeitsnotebook
├── requirements.txt       # Python-Abhängigkeiten
├── Anforderungen.md       # Diese Datei
└── data/
    └── Förderverein_HGO_Satzung.pdf  # PDF für Phase 2
```

---

## Tipps

- Führt die Zellen im Notebook **der Reihe nach** aus
- Lest die Markdown-Zellen sorgfältig, sie enthalten wichtige Hinweise
- Bei Fehlern: Überprüft, ob Ollama läuft (`ollama serve`)
- Nutzt die verlinkten Ressourcen bei Fragen

---

**Viel Erfolg!**