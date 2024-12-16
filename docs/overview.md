### **docs/overview.md**
```markdown
# Projektöversikt

## Bakgrund
Detta projekt utforskar användningen av AI och virtualisering för att simulera en arbetsmiljö där flera agenter samarbetar. Projektet är tänkt att vara ett verktyg för att förstå AI-baserad samverkan och dess potential.

## Mål
- Definiera agentroller och deras interaktioner.
- Bygga en robust backend för att stödja AI-agenter.
- Visualisera simuleringen i realtid med Mesa.
- Testa skalbarhet och samordning mellan flera agenter.

## Teknologier

- **CrewAI:** För att hantera agenternas roller, samarbete och delegation.
- **Docker:** För att köra varje agent i en isolerad miljö och möjliggöra enkel skalbarhet.
- **OpenAI API:** För att tillhandahålla AI-funktionalitet till agenterna.
- **Python och FastAPI:** För att bygga backend och skapa API-endpoints.

## YAML-baserad konfiguration

All konfiguration för agenter och uppgifter kommer att definieras i YAML-filer, som är kompatibla med CrewAI.

Exempel:
agents.yaml: Definierar agenter och deras egenskaper.
tasks.yaml: Specificerar uppgifter och deras beroenden.