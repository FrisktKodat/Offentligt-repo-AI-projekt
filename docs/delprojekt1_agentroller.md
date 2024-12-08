# Delprojekt 1: Agentroller och Basfunktioner

## Mål
Detta delprojekt fokuserar på att skapa de första AI-agenterna som ska simulera olika roller. Vi börjar med att definiera en **utvecklaragent** och implementera grundläggande funktionalitet för att simulera hur denna agent arbetar.

---

## Funktioner
### **1. Definiera utvecklaragentens roll**
- **Ansvar:** Skapa och förbättra kod baserat på specifikationer.
- **Input:** Beskrivningar av uppgifter från användaren eller projektledaren.
- **Output:** Kod som kan användas i projektet.

### **2. Simulera agentens beteende**
- Använd OpenAI API (Codex eller GPT-modeller) för att generera kod baserat på specifikationer.
- Implementera en enklare fallback-funktion om API inte är tillgängligt.

### **3. Isolera agentens miljö**
- Kör agenten i en Docker-container för att skapa en skalbar och säker exekveringsmiljö.

---

## Teknisk Implementation
### **1. Skapa en Python-klass för utvecklaragenten**
- Implementera klassen `DeveloperAgent` i filen `agents/developer.py`.
- Exempel:
    ```python
    class DeveloperAgent:
        def __init__(self, name: str):
            self.name = name

        def generate_code(self, task_description: str) -> str:
            # Placeholder för AI-generering
            return f"# Code generated for: {task_description}"
    ```

### **2. API för utvecklaragenten**
- Skapa en REST-API-endpoint i `api/routes/developer_routes.py`.
- Exempel:
    ```python
    from fastapi import APIRouter, HTTPException

    router = APIRouter()

    @router.post("/developer/generate-code/")
    async def generate_code(task: str):
        if not task:
            raise HTTPException(status_code=400, detail="Task description is required")
        # Anropa DeveloperAgent och generera kod
        developer = DeveloperAgent("Agent-1")
        code = developer.generate_code(task)
        return {"task": task, "code": code}
    ```

### **3. Docker-konfiguration**
- Skapa en Dockerfile specifik för utvecklaragenten:
    ```dockerfile
    FROM python:3.10-slim
    WORKDIR /app
    COPY . /app
    RUN pip install -r requirements.txt
    CMD ["python", "api/main.py"]
    ```

---

## Testplan
1. **Enhetstester:**
   - Testa `generate_code`-funktionen med olika beskrivningar.
   - Skapa en testfil: `tests/test_developer.py`.
2. **Integrationstester:**
   - Verifiera att API-anrop returnerar korrekt genererad kod.
3. **Manuella tester:**
   - Kör agenten i Docker och testa interaktionen via API.

---

## Leveranser
- Python-klass `DeveloperAgent` med grundläggande funktionalitet.
- API-endpoint för att interagera med utvecklaragenten.
- Docker-miljö för isolerad körning av agenten.
- Dokumentation och tester.

---

## Nästa steg
Efter implementeringen av utvecklaragenten går vi vidare till:
1. Utveckling av testaren i Delprojekt 4.
2. Integration med andra agenter i Delprojekt 2.
