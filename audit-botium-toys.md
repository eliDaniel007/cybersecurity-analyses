# Audit de sécurité interne — Botium Toys

> Évaluation de la posture de sécurité d'une PME fictive (Botium Toys) et plan d'atténuation priorisé.

## Contexte
Botium Toys, un magasin de jouets en expansion (boutique + ventes en ligne), doit s'assurer que son infrastructure IT est prête à soutenir sa croissance tout en respectant les réglementations. On m'a confié un **audit de sécurité interne** afin d'établir la portée, d'évaluer les risques et de recommander des contrôles.

## Portée & objectif
- **Portée** : l'ensemble des actifs et systèmes de l'entreprise (employés, équipement, matériel réseau, périmètre physique).
- **Objectif** : évaluer les contrôles existants et la conformité, puis prioriser les correctifs.

## Méthode
1. **Évaluation des risques** — identification des actifs, des menaces et des vulnérabilités.
2. **Revue des contrôles** — 14 contrôles évalués (administratifs, techniques, physiques).
3. **Revue de conformité** — 12 exigences (**PCI DSS**, **RGPD**, **SOC type 1/2**).

## Constats
- **Score de risque global : 8/10 (élevé).** Croissance rapide sans renforcement proportionnel des contrôles.
- Lacunes majeures : **contrôle d'accès insuffisant**, **absence de chiffrement** des données sensibles, **gestion des mots de passe** faible, **journalisation / détection d'intrusion** limitées.
- Données à protéger : **PII / SPII** des clients et employés — exposition réglementaire (RGPD, PCI DSS).

## Recommandations priorisées
| Priorité | Contrôle | Objectif |
|---|---|---|
| Élevée | Moindre privilège & gestion des accès | Limiter l'exposition des données sensibles |
| Élevée | Chiffrement au repos et en transit | Protéger PII/SPII et données de paiement (PCI DSS) |
| Élevée | Politique de mots de passe + MFA | Réduire le risque de compromission de comptes |
| Moyenne | Journalisation & détection d'intrusion (IDS) | Détecter et tracer les incidents |
| Moyenne | Plan de continuité / sauvegardes | Résilience en cas d'incident |

## Compétences démontrées
Gestion des risques · cadres NIST · conformité PCI DSS / RGPD / SOC · définition de contrôles · plan d'atténuation.
