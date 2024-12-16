# Huvudprojekt - AI med Virtualisering

Detta projekt syftar till att simulera en AI-driven arbetsmiljö där agenter med olika roller (utvecklare, testare, projektledare) samarbetar i en virtualiserad miljö. Genom att använda CrewAI och Docker bygger vi en skalbar och flexibel plattform för AI-agentbaserad samverkan.

## Mål
- Skapa en simulering med AI-agenter som interagerar och löser arbetsuppgifter.
- Använda Mesa för att visualisera interaktioner i realtid.
- Etablera en skalbar infrastruktur baserad på Docker och Python.

## Projektstruktur
- **Delprojekt 1:** Agentroller och basfunktioner.
- **Delprojekt 2:** Kommunikation och orkestrering.
- **Delprojekt 3:** Frontend och visualisering.
- **Delprojekt 4:** Integration av testning.
- **Delprojekt 5:** Projektledning och koordinering.

- **CrewAI + Docker:** Projektet använder CrewAI för att hantera agenternas roller och samarbete. Varje agent körs i en isolerad Docker-container för skalbarhet.
- **OpenAI API:** Alla agenter använder OpenAI API från början för att utföra sina uppgifter. Detta ger avancerad AI-funktionalitet utan behov av att utveckla egna modeller.

## Teknisk implementation

- CrewAI hanterar orkestreringen av agenterna och deras samarbete.
- OpenAI API används för att generera kod, analysera text och utföra andra AI-relaterade uppgifter.
- Docker används för att isolera och skala agenternas miljö.
- Vi kommer att använda CrewAI:s inbyggda stöd för lokala LLM:er via LiteLLM. Detta inkluderar modeller som Ollama, LLaMA 2 och Mistral.
- All konfiguration för agenter och uppgifter kommer att definieras i YAML-filer, som är kompatibla med CrewAI.
- Vi kommer att lagra API-nycklar och annan känslig information i en .env-fil för att öka säkerheten och förenkla hantering av miljövariabler.

## Installation
1. Klona repositoryt:
   ```bash
   git clone https://github.com/FrisktKodat/Offentligt-repo-AI-projekt.git
   cd Offentligt-repo-AI-projekt

## Installera beroenden:
pip install -r requirements.txt

## Användning
Kör simuleringen:
python mesa/simulation.py

## Visualisering
Simuleringen är tillgänglig i webbläsaren på http://localhost:8521.

## Dokumentation
Översikt
Arkitektur
Agentroller

## Metodologi
Agil utveckling: Arbeta i sprintar där varje delprojekt adresseras iterativt.
Versionskontroll: Använd GitHub för att dokumentera, spåra och hantera kodändringar.
Dokumentation: Fokusera på att beskriva varje delprojekt tydligt, med tekniska detaljer och framsteg.