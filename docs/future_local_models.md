# Framtida Plan för Lokala Modeller

## Syfte
Denna sektion beskriver hur lokala AI-modeller kan införas i projektet som ett komplement eller alternativ till OpenAI API. Målet är att minska kostnader, öka kontrollen över data och möjliggöra offline-bearbetning.

---

## Fördelar med Lokala Modeller
1. **Kostnadsbesparingar:** Ingen kostnad för API-anrop efter installation.
2. **Datakontroll:** Alla uppgifter och bearbetningar sker lokalt, vilket minskar risker kopplade till dataläckage.
3. **Tillgänglighet:** Möjlighet att köra modeller utan internetanslutning.
4. **Flexibilitet:** Använd olika lokala modeller beroende på uppgiftens komplexitet.

---

## Plan för Integration

### **1. Initial Setup**
1. **Identifiera användningsområden:**
   - Uppgifter som kräver mindre kontext eller bearbetning (t.ex., generera enkla kodstycken, textklassificering).
2. **Välj en lokal modell:**
   - Lämpliga alternativ inkluderar:
     - **LLaMA 2 (7B eller 13B):** Optimerad för begränsade resurser.
     - **Mistral:** För snabba och lätta inferenser.
     - **Ollama:** För enkel installation och användning.
     - **Phi:** För experimentella ändamål.

3. **Förbered servermiljön:**
   - Kontrollera serverresurserna (CPU och RAM) och säkerställ att de kan stödja den valda modellen.

---

### **2. Docker-Integration**
1. **Skapa en Docker-container för den lokala modellen:**
   - Exempel för LLaMA 2:
     ```dockerfile
     FROM pytorch/pytorch:2.0.1-cuda11.7-cudnn8-runtime
     WORKDIR /app
     RUN pip install transformers accelerate
     COPY . /app
     CMD ["python", "local_model_server.py"]
     ```

2. **Lägg till container i Docker Compose:**
   - Uppdatera `docker-compose.yml`:
     ```yaml
     local_model:
       build:
         context: ./local_model
         dockerfile: Dockerfile
       ports:
         - "6000:6000"
       environment:
         - MODEL_TYPE=llama-2-7b
     ```

---

### **3. Agentanpassning**
- Uppdatera agenternas abstraktion för att möjliggöra val mellan OpenAI API och lokal modell.
- Exempel:
  ```python
  class BaseAgent:
      def query_model(self, prompt):
          if self.model_type == "local":
              return self.query_local_model(prompt)
          else:
              return self.query_openai_api(prompt)
