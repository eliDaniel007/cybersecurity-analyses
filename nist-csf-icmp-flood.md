# Réponse à incident selon le NIST CSF — ICMP flood

> Application des 5 fonctions du NIST Cybersecurity Framework à une attaque DoS de type ICMP flood.

## Contexte
Une entreprise subit une **attaque par déni de service de type ICMP flood** exploitant un **pare-feu mal configuré** (qui laissait passer un volume illimité de requêtes ICMP « echo »). J'ai structuré la réponse selon le **NIST CSF**.

## Analyse
- L'attaquant inonde le réseau de paquets **ICMP echo request (ping)**.
- Le pare-feu, mal configuré, n'impose **aucune limite** → saturation de la bande passante et des ressources.
- Résultat : **indisponibilité** des services internes pour les employés.

## Réponse selon les 5 fonctions du NIST CSF

| Fonction | Mesures |
|---|---|
| **Identifier** | Cartographier les actifs exposés ; repérer la règle pare-feu défaillante et la source du trafic ICMP. |
| **Protéger** | Reconfigurer le pare-feu : **limiter/filtrer l'ICMP**, appliquer une **limitation de débit**, principe du moindre privilège réseau. |
| **Détecter** | Règles **IDS** et alertes sur les pics de trafic ICMP ; surveillance de la bande passante. |
| **Répondre** | Bloquer la source, appliquer les filtres, communiquer aux parties prenantes, documenter l'incident. |
| **Récupérer** | Rétablir les services, vérifier l'intégrité, tirer les leçons (revue de configuration pare-feu). |

## Justification
Chaque mesure est justifiée techniquement : le point de défaillance étant une **règle pare-feu trop permissive**, la protection prioritaire est le **filtrage/limitation de l'ICMP**, complétée par la détection pour éviter la récidive.

## Compétences démontrées
Cadre **NIST CSF** · réponse à incident · durcissement pare-feu · plan de protection / détection / réponse / récupération.
