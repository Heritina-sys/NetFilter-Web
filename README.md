# NetFilter Web

Variante « web » du projet **NetFilter** : interface PHP/Bootstrap de gestion
d'`iptables` depuis un navigateur.

## Contenu

Le dossier racine contient l'application complète dans le sous-dossier
`NetFilter/` :

- `Netfilter.php` — classe de lecture d'iptables et de construction des commandes
- `iptables.php` — affichage des règles INPUT / OUTPUT / FORWARD
- `ajout.php` et `traitement.php` — formulaire d'ajout et traitement
- `div.js`, `iptables.js`, `iptables.css`
- `bootstrap/` — Bootstrap 5
- `Images/` — captures d'écran et icônes (dont `pare-feu.png` et `rafraichir.png`)
- `service` et `iptables` — données de référence et sortie générée

## Fonctionnalités

- Lecture des règles avec `sudo iptables -S`.
- Tableaux colorés selon l'action (`ACCEPT`, `DROP`, `REJECT`).
- Ajout de règles (chaîne, action, interface, protocole, MAC, ports, source,
  destination).
- Navigation Home / Input / Output / Forward.

## Prérequis

- PHP 7 ou 8
- Serveur web (Apache, Nginx ou `php -S`)
- Linux avec `iptables`
- Droits suffisants pour exécuter `sudo iptables` (idéalement `sudo` sans mot
  de passe pour l'utilisateur du serveur web)

## Lancement

```bash
cd NetFilter
php -S localhost:8000
# puis http://localhost:8000/iptables.php
```

## Sécurité

Comme pour `NetFilter`, l'application exécute des commandes système via `exec()`
et `sudo`, sans authentification. **À ne pas exposer sur un réseau non fiable**
et à valider strictement avant tout usage réel.

## Note

Ce dépôt est une copie archivée très proche du dépôt `NetFilter`, avec quelques
images supplémentaires. Seul le sous-dossier `NetFilter/` contient l'application.
