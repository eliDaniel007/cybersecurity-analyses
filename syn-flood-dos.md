# Analyse d'incident — Attaque par déni de service (SYN flood)

> Diagnostic d'une interruption de service web à partir d'une capture Wireshark TCP/HTTP.

## Contexte
Les utilisateurs d'un site web signalent des **temps de réponse anormalement longs**, puis une **indisponibilité**. Une capture réseau (Wireshark) est fournie pour déterminer la cause.

## Méthode d'investigation
1. Ouverture de la capture et filtrage du trafic **TCP** vers le serveur web.
2. Observation des **poignées de main TCP** (three-way handshake).
3. Corrélation avec les réponses **HTTP** et les paquets de réinitialisation.

## Constats (preuves)
- **Volume anormal de paquets `SYN`** provenant d'une **adresse IP source unique**, à très haute fréquence.
- **Poignées de main incomplètes** : le serveur répond `SYN, ACK` mais l'`ACK` final n'arrive jamais → connexions laissées **half-open**.
- Apparition de paquets **`RST`/`ACK`** et d'erreurs **HTTP 504 (Gateway Timeout)** à mesure que les ressources du serveur s'épuisent.

## Cause probable
**Attaque par déni de service de type SYN flood** : l'attaquant sature la table des connexions du serveur avec des demandes de connexion jamais finalisées, épuisant les ressources et rendant le service indisponible pour les utilisateurs légitimes.

## Recommandations
- Activer les **SYN cookies** sur le serveur.
- Mettre en place **limitation de débit** et filtrage au niveau du **pare-feu**.
- Détection : **alerte** sur le taux de `SYN` sans `ACK` final (règle IDS).
- Bloquer / mettre en liste noire l'IP source, surveiller la récidive.

## Compétences démontrées
Analyse de trafic réseau · Wireshark · protocole TCP · identification d'attaque DoS · rédaction d'un rapport d'incident étayé.
