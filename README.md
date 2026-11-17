# Agenti AI Insieme

Istruzioni pubbliche per collegare gli assistenti AI ai servizi Insieme.
La prima integrazione documentata è **CasaGest MCP**, con accesso personale
tramite OAuth InsiemeID.

## Per iniziare

Copia il breve [prompt di avvio](PROMPT.md) nel tuo assistente. La configurazione
completa, le differenze tra piattaforme e le regole operative sono in
[INSTRUCTIONS.md](INSTRUCTIONS.md).

- **Istruzioni raw:** https://raw.githubusercontent.com/Insieme-srl/llm_agents/main/INSTRUCTIONS.md
- **Endpoint MCP:** https://mcp.gruppoinsieme.it/mcp
- **Trasporto:** Streamable HTTP remoto, con OAuth.
- **Accesso:** utente e agenzia derivano dal login, non da identificativi inseriti
  nella chat.

Il dominio senza `/mcp` è una pagina web, non l’endpoint del protocollo.
Un prompt può guidare la configurazione, ma non aggiunge da solo un connettore
a una piattaforma che richiede un intervento nelle impostazioni.

**Claude web:** se il login automatico fallisce o richiede un OAuth Client ID,
segui la [procedura dedicata](INSTRUCTIONS.md#claude-web), con il documento
pubblico già disponibile e il segreto vuoto. Un errore di registrazione, da solo,
non prova un problema DCR. Verifica poi il login dal connettore Claude.

**Mistral web:** segui la [procedura dedicata](INSTRUCTIONS.md#mistral-web).
Il campo «ID client» usa il documento pubblico già predisposto per questa
integrazione; non occorre cercare una voce CIMD nel menu o inventare credenziali.
Il login completo va comunque verificato dal connettore Mistral.

## Contenuto

| File | Scopo |
|---|---|
| [INSTRUCTIONS.md](INSTRUCTIONS.md) | Guida completa per utenti e assistenti; include la sezione `RULES`. |
| [PROMPT.md](PROMPT.md) | Unico breve testo da copiare nella conversazione. |
| [oauth/casagest-mcp-remote.json](oauth/casagest-mcp-remote.json) | Identità OAuth pubblica del ponte locale `mcp-remote`, senza segreti. |
| [oauth/casagest-mistral-web.json](oauth/casagest-mistral-web.json) | Identità OAuth pubblica predisposta da Insieme per il connettore CasaGest su Mistral web; flusso completo da collaudare. |
| [oauth/casagest-claude-web.json](oauth/casagest-claude-web.json) | Identità OAuth pubblica predisposta da Insieme per il connettore CasaGest su Claude web; flusso completo da collaudare. |

Le istruzioni coprono OpenCode, Claude, Cursor, VS Code, ChatGPT e Mistral web. Preferisci
HTTP remoto nativo; usa il ponte stdio soltanto quando necessario. La guida
distingue gli esempi di configurazione dai collegamenti effettivamente collaudati.

## Riservatezza

Questo repository contiene soltanto documentazione e metadata pubblici.
Non pubblicare account reali, dati di immobili o clienti, token, codici OTP,
URL di callback completi, password, esportazioni del database o log non oscurati.
Le richieste di assistenza su dati personali vanno trattate nei canali privati.
