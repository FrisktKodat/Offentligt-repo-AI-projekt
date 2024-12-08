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

- **API:**
  Backend byggd med FastAPI, hanterar agenternas kommunikation.

- **Visualisering:**
  Mesa används för att visualisera simuleringen i realtid.

## Flöde
1. En användare initierar en simulering via frontend.
2. Agenter utför sina roller baserat på uppgifter.
3. Resultaten visas i Mesa-gränssnittet.
