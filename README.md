# SYS://ADMIN — Terminal de Formation v3

Application web interactive d'apprentissage de l'administration système, couvrant **Linux** et **Windows Server** en 20 modules progressifs.

## Apercu

SYS://ADMIN est une plateforme e-learning single-page (SPA) entierement client-side, deployable comme un simple fichier HTML statique. Elle combine cours theoriques, quiz et labs interactifs dans une interface au style terminal/retro.

## Fonctionnalites

| Fonctionnalite | Description |
|---|---|
| **Cours** | Contenu riche avec blocs de code, tips et warnings |
| **Quiz** | 5 QCM par module avec feedback instantane et score |
| **Labs terminal** | Simulation de terminal Bash (Linux) et PowerShell (Windows) avec validation de commandes |
| **GUI Windows** | Simulation d'interfaces graphiques : Active Directory, Hyper-V Manager, DNS/DHCP, Event Viewer, PKI... |
| **Progression** | Suivi persistant via `localStorage` (modules lus, scores quiz, labs completes) |

## Modules

### Linux (10 modules)

| # | Module | Niveau |
|---|--------|--------|
| 0 | Le Terminal : Premiers Pas | Debutant |
| 1 | Systeme de Fichiers | Debutant |
| 2 | Permissions et Proprietes | Intermediaire |
| 3 | Utilisateurs et Groupes | Intermediaire |
| 4 | Gestion des Processus | Intermediaire |
| 5 | Reseau Linux | Avance |
| 6 | Services et systemd | Avance |
| 7 | SSH et Securite | Avance |
| 8 | Stockage et LVM | Expert |
| 9 | Automation et Scripting | Expert |

### Windows Server (10 modules)

| # | Module | Niveau |
|---|--------|--------|
| 10 | PowerShell : Les Bases | Debutant |
| 11 | Windows Server : Roles | Debutant |
| 12 | Active Directory | Intermediaire |
| 13 | GPO : Strategies de Groupe | Intermediaire |
| 14 | DHCP et DNS Server | Intermediaire |
| 15 | Partages SMB, NTFS, DFS | Avance |
| 16 | Hyper-V : Virtualisation | Avance |
| 17 | Certificats et PKI | Avance |
| 18 | Monitoring et Event Viewer | Expert |
| 19 | Windows Automation Expert | Expert |

## Stack technique

- **HTML/CSS/JS** vanilla — aucun framework
- **Fonts** : Fira Code, Share Tech Mono (Google Fonts)
- **Theming** : variables CSS avec theme sombre (Linux) et theme clair style Windows 95 (Windows)
- **Persistance** : `localStorage` (cle `sysadmin-v3`)
- **Deploiement** : fichier unique `sysadmin-v3.html`, aucun backend requis

## Architecture

```
sysadmin-v3.html        # Application complete (SPA monofichier)
├── <style>             # CSS : layout flex, themes, terminal, GUI Windows
├── <body>              # Structure : sidebar + zone principale a onglets
└── <script>
    ├── M[]             # Tableau des 20 modules (cours, quiz, labs)
    ├── State (st)      # Etat global + sync localStorage
    ├── Rendering       # Fonctions de rendu (rS, rC, rCourse, rQuiz, rLab)
    ├── Terminal sim    # Simulation terminal (subC, renderTerminal)
    └── GUI sim         # Simulation GUI Windows (AD, Hyper-V, DNS, GPO...)
```

## Utilisation

Ouvrir `sysadmin-v3.html` dans un navigateur. Aucune installation requise.

La progression est sauvegardee automatiquement dans le navigateur.

## Licence

Projet prive.
