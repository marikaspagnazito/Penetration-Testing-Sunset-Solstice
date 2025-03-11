# Sunset: Solstice - Penetration Testing Report

## Descrizione
Questo progetto documenta l'analisi di sicurezza condotta sulla macchina virtuale *Sunset: Solstice*, disponibile su [VulnHub](https://www.vulnhub.com/entry/sunset-solstice,499/). L'obiettivo è identificare vulnerabilità e dimostrare tecniche di exploit nel contesto di un *penetration testing* etico.

## Contenuto della Repository
Questa repository contiene i seguenti file:

- **Rapporto di scansione 
dettagliato**: Un file che descrive dettagliatamente tutte le fasi del penetration testing, illustrando le tecniche e gli strumenti utilizzati.
- **Report Finale**: Un documento che raccoglie i risultati dell'analisi, le vulnerabilità individuate e le strategie di mitigazione.
- **Presentazione**: Una presentazione che riassume il lavoro svolto e i principali risultati ottenuti.

## Struttura del Progetto
Il report segue il framework standard per il penetration testing:

1. **Information Gathering** - Raccolta di informazioni sul target.
2. **Target Discovery** - Identificazione della macchina e del sistema operativo.
3. **Port Scanning & Enumeration** - Scansione delle porte e servizi attivi.
4. **Vulnerability Mapping** - Analisi manuale e automatica delle vulnerabilità.
5. **Target Exploitation** - Sfruttamento delle vulnerabilità per ottenere accesso.
6. **Post-Exploitation** - Escalation dei privilegi e persistenza dell’accesso.
7. **Remediation** - Strategie di mitigazione per le vulnerabilità scoperte.

## Strumenti Utilizzati

- **Virtualizzazione**: Oracle VM VirtualBox
- **Sistema Attaccante**: Kali Linux 2024.1
- **Strumenti di Scansione**: `nmap`, `netdiscover`, `unicornscan`
- **Analisi delle Vulnerabilità**: Nessus, OpenVAS, OWASP ZAP, Nikto2
- **Exploitation**: Burp Suite, Metasploit, Reverse Shell (PentestMonkey)

## Vulnerabilità Scoperte

- **Sistema Operativo obsoleto** - Fine ciclo di vita, non più supportato.
- **Apache 2.4.38** - Versione obsoleta con vulnerabilità note.
- **PHP 7.3.14** - Versione affetta da multiple vulnerabilità.
- **Local File Inclusion (LFI)** - Possibile accesso a `/etc/passwd`.
- **Log Poisoning** - Escalation da LFI a RCE.
- **Credenziali in Chiaro** - Accesso root tramite file `config.php`.
- **Accesso anonimo FTP** - Permette potenziali accessi non autorizzati.
- **Header di sicurezza mancanti** - Assenza di X-Frame-Options e Content Security Policy.

## Exploitation

- **Esecuzione di codice remoto (RCE)** tramite LFI e log poisoning.
- **Reverse Shell** ottenuta con *Netcat*.
- **Privilege Escalation** tramite credenziali in chiaro e manipolazione di processi.
- **Accesso Persistente** tramite backdoor PHP con *Meterpreter*.

## Possibile Remediation

- **Aggiornamento del sistema operativo e del software** per eliminare vulnerabilità obsolete.
- **Abilitazione degli header di sicurezza** come X-Frame-Options e Content Security Policy.
- **Rimozione dell'accesso anonimo FTP** e impostazione di permessi adeguati.
- **Crittografia delle credenziali sensibili** e utilizzo di password sicure.

## Come Utilizzare il Report

- Seguire il report per replicare il penetration test.
- Usare il report come riferimento per pratiche di sicurezza.
- Non utilizzare per scopi non etici.

## Autore

**Marika Spagna Zito**  
Università degli Studi di Salerno - Corso di PTEH (A.A. 2023/2024)

## Disclaimer

Questo progetto è destinato esclusivamente a scopi educativi. Il penetration testing deve essere eseguito solo su macchine per cui si dispone dell'autorizzazione.

