# Contribuții

## Cum poți contribui

### 1. Adaugi un agent nou pentru o facultate / persoană

Vezi `INSTRUCTIONS.md` și `AGENTS.md` pentru ghidul complet.

Pe scurt:
1. Creează fișierul de profil în `filter/NUME.md` (competențele persoanei / curriculum)
2. Creează agentul în `agents/NUME.md`
3. Actualizează `conf/local_tag.md`
4. Rulează `node scripts/fetch_agent_jobs.mjs` pentru a genera `jobs.json`

### 2. Corectezi matching-ul existent

Dacă găsești un job greșit etichetat în `jobs.json`:
1. Fă un fork al repository-ului
2. Corectează câmpurile (`f_tag`, `matchPercentage`, `reason`)
3. Deschide un Pull Request

### 3. Raportezi o problemă

Deschide un [Issue](../../issues) cu:
- descrierea problemei
- cum poate fi reprodusă
- capturi de ecran (dacă e cazul)

### 4. Îmbunătățești documentația

Orice clarificare în `README.md`, `AGENTS.md`, `STRUCTURE.md` sau `INSTRUCTIONS.md` e binevenită.

## Rules

- Respectă structura existentă a fișierelor JSON (vezi `STRUCTURE.md`)
- Verifică întotdeauna că URL-urile din `jobs.json` sunt accesibile
- Folosește nume sugestive pentru branch-uri (`fix/typo-jobs`, `feat/new-agent-ubb`)
- Toate PR-urile trec prin code review
