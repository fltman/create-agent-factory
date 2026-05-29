# Agent Factory 🏭

Ett självorganiserande agent-team som bygger sig självt. Agenter som rekryterar agenter.

I stället för att handskapa ett team startar du med två kärnagenter, CEO och HR, som bygger upp resten utifrån projektets behov. CEO intervjuar dig, HR skapar kandidater, du väljer vilka som anställs. Alla agenter kan sedan be HR om nya kollegor när de upptäcker att en kompetens saknas.

Det här är det första av tre tankesätt om agentteam. Det använder mänskliga mönster: ett företag med roller, intervjuer och anställning. Se även syskonen [HIVE](https://github.com/fltman/create-hive-product) (alien-mönster, capabilities utan hierarki) och [FLUX](https://github.com/fltman/create-flux-product) (biologiska mönster, evolution).

```
agera som ett företag  ->  agera som sig själv  ->  evolvera till vad som funkar
   Agent Factory               HIVE                       FLUX
```

## Så fungerar det

1. **Projektstart.** `/start` och CEO intervjuar dig om vad som ska byggas.
2. **Teamanalys.** CEO identifierar vilka roller som behövs.
3. **Rekrytering.** CEO skickar en rekryteringsorder till HR, som skapar tre kandidatvarianter (Specialist, Generalist, Innovator).
4. **Intervju.** CEO och HR intervjuar kandidaterna, du väljer vinnaren.
5. **Expansion.** Alla agenter kan be HR om nya kollegor. Teamet växer organiskt.

## Kommandon

| Kommando | Beskrivning |
|----------|-------------|
| `/start` | Starta nytt projekt, CEO intervjuar dig |
| `/recruit` | Rekrytera en ny agent till teamet |
| `/team` | Visa nuvarande team och roller |

## Generella agenter (fast personal)

Utöver CEO och HR följer fabriken med generella agenter som alltid finns på plats. HR rekryterar projektspecifika specialister, men de här kan teamet använda direkt från start.

| Agent | Roll |
|-------|------|
| `image-creator` | Bildgenerering (Gemini) |
| `elevenlabs-voice` | Röst och dialog (ElevenLabs) |
| `suno-songwriter` | Låtskrivande och musik (Suno) |

De drivs av en valfri verktygslåda i `.claude/skills/`: `gemini-imagegen`, `sora-video`, `suno-music-skill`, `elevenlabs-skill`. Ignorera den för rena kod- eller researchprojekt. Media-skills kräver API-nycklar, kopiera `.env.example` till `.env` och fyll i det du har.

## Snabbstart

```bash
git clone https://github.com/fltman/create-agent-factory.git
cd create-agent-factory
claude
/start
```

## Struktur

```
.claude/
  agents/
    ceo.md              projektledare
    hr.md               agent-arkitekt och rekryterare
    image-creator.md    generell agent: bild
    elevenlabs-voice.md generell agent: röst
    suno-songwriter.md  generell agent: musik
    candidates/         temporära kandidater under rekrytering
  commands/             start, recruit, team
  skills/               valfri verktygslåda (bild, video, musik, röst)
CLAUDE.md               konceptet och processen
```

## Designprinciper

- **Progressive team building.** Börja smått, väx efter behov.
- **Human in the loop.** Du godkänner alla rekryteringar.
- **Specialisering.** Varje agent har ett tydligt fokus.
- **Självorganisering.** Agenter kan upptäcka egna behov och rekrytera kollegor.
