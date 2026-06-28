# Job Widget UBBFPSE — Filtrare inteligentă a locurilor de muncă

**Filtrare inteligentă a locurilor de muncă folosind AI** pentru studenții Facultății de Psihologie și Științe ale Educației, Universitatea Babeș-Bolyai.

## Ideea proiectului

Colectăm locuri de muncă de pe [peviitor.ro](https://peviitor.ro) și, pe baza unui profil AI generat din curriculum-ul facultății, determinăm ce joburi se potrivesc pentru un student al facultății.

## Stack tehnologic

- **OpenCode** – agent AI pentru matching inteligent
- **GitHub Actions** – automatizare pipeline (generare curriculum, agent, matching)
- **Peviitor.ro** – sursa principală de date (joburi)

## Cum funcționează

1. **Curriculum**: Se extrage planul de învățământ din sursa oficială și se salvează în `filter/UBBFPSE.md`
2. **Agent**: Se generează profilul studentului (`agents/student.md`) pe baza curriculum-ului
3. **Matching**: Scriptul `scripts/fetch_agent_jobs.mjs` caută joburi în API-ul Peviitor, le evaluează cu agentul AI și salvează rezultatele în `jobs.json`
4. **Widget**: Frontend-ul afișează joburile potrivite

## Configurare locală

În `conf/local_tag.md` se definește tag-ul facultății și sursa curriculum-ului:

```
UBBFPSE sursa: https://psiedu.ubbcluj.ro
```

## Pipeline

| Pas | Acțiune | Output |
|-----|---------|--------|
| 1 | `node scripts/generate_curriculum.mjs` | `filter/UBBFPSE.md` |
| 2 | `node scripts/generate_student_agent.mjs` | `agents/student.md` |
| 3 | `node scripts/fetch_agent_jobs.mjs` | `jobs.json` |

Vezi `INSTRUCTIONS.md` și `AGENTS.md` pentru detalii complete.

## Widget Incorporabil

Widget-ul poate fi încorporat pe orice site printr-un `<iframe>`:

```html
<iframe
  src="https://emtreila.github.io/jobs-widget-ubbfpse/#/widget?tag=UBBFPSE&title=Joburi%20UBBFPSE&color=blue"
  width="100%"
  height="650px"
></iframe>
```

## Licență

Acest proiect este distribuit sub licența **MIT**. Vezi fișierul [LICENSE](LICENSE).

## Contribuții

Contribuțiile sunt binevenite! Vezi [CONTRIBUTING.md](CONTRIBUTING.md) și [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) pentru detalii.
