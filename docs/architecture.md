# Arkitekturbeskrivning

## Översikt
Systemet är uppdelat i flera komponenter:
1. **AI-agenter:** Individuella agenter som utför specifika roller.
2. **API:** Kommunicerar mellan agenter och frontend.
3. **Visualisering:** Använder Mesa för att visa simuleringens status.
4. **Infrastruktur:** Docker för containerhantering och TrueNAS Scale som värd.

## Komponenter
- **Agenter:**
  - `developer.py`: Skapar och förbättrar kod.
  - `tester.py`: Utför automatiserade tester.
  - `project_manager.py`: Koordinerar arbetsflödet.

### CrewAI
CrewAI hanterar agenter som simulerar roller som utvecklare, testare och projektledare. Det används för att definiera agenternas beteenden och orkestrera arbetsflöden.

### Docker
Varje agent körs i en separat Docker-container, vilket möjliggör isolering och skalbarhet. Docker Compose används för att hantera flera containrar.

### OpenAI API
Agenterna använder OpenAI API från början för att utföra sina uppgifter, såsom kodgenerering och textbearbetning. Detta säkerställer hög AI-prestanda och flexibilitet.


- **API:**
  Backend byggd med FastAPI, hanterar agenternas kommunikation.

- **Visualisering:**
  Mesa används för att visualisera simuleringen i realtid.

## Flöde
1. En användare initierar en simulering via frontend.
2. Agenter utför sina roller baserat på uppgifter.
3. Resultaten visas i Mesa-gränssnittet.
