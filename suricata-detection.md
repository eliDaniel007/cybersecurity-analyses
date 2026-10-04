# Détection d'intrusion réseau avec Suricata

> Écriture de règles Suricata personnalisées et analyse des journaux pour détecter une activité malveillante.

## Contexte
Mise en place d'une **détection d'intrusion (IDS/NIDS)** avec **Suricata** : création de règles sur mesure, génération d'alertes, puis corrélation des événements dans les journaux.

## Démarche
1. **Règles personnalisées** — écriture de signatures (`alert ...`) ciblant un trafic suspect (ex. connexions vers un hôte/port malveillant, motif dans la charge utile).
2. **Génération d'alertes** — exécution de Suricata sur le trafic ; vérification dans **`fast.log`** (alertes lisibles) et **`eve.json`** (événements structurés).
3. **Investigation** — analyse des champs de `eve.json` et **corrélation des événements par `flow_id`** à l'aide de **`jq`** pour reconstituer une session complète.

## Exemple de règle
```
alert http any any -> any any (msg:"Téléversement suspect"; flow:established,to_server; \
  http.method; content:"POST"; http.uri; content:"/upload"; sid:1000001; rev:1;)
```

## Constats
- Les alertes `fast.log` donnent une vue rapide ; `eve.json` permet l'analyse fine et l'automatisation.
- Le `flow_id` relie plusieurs événements (alerte, HTTP, fichier) d'une **même connexion** → reconstitution de l'incident.

## Compétences démontrées
IDS/NIDS · règles Suricata · analyse de journaux `fast.log` / `eve.json` · corrélation d'événements · `jq` · détection réseau.
