# Analyse d'indicateurs de compromission (IoC) & pyramide de la douleur

> Identification et qualification d'indicateurs de compromission à l'aide de VirusTotal et de la pyramide de la douleur.

## Contexte
Un fichier suspect est associé à une campagne de logiciel malveillant (**Flagpro**, attribuée au groupe **BlackTech**). J'analyse les **indicateurs de compromission (IoC)** et j'évalue leur valeur défensive avec la **pyramide de la douleur**.

## Démarche
1. **Empreinte du fichier** — calcul du **hash SHA-256** du binaire suspect.
2. **Enrichissement** — soumission du hash à **VirusTotal** : détections multi-moteurs, domaines/IP associés, comportements observés.
3. **Qualification** — classement des IoC selon la **pyramide de la douleur** (de la plus facile à la plus coûteuse à changer pour l'attaquant).

## Pyramide de la douleur
| Niveau | IoC | « Douleur » pour l'attaquant |
|---|---|---|
| Bas | Hash de fichier | Trivial à changer |
| ↓ | Adresses IP | Facile |
| ↓ | Noms de domaine | Modéré |
| ↓ | Artefacts réseau/hôte | Ennuyeux |
| ↓ | Outils | Difficile |
| Haut | **TTP** (tactiques, techniques, procédures) | Très coûteux |

> **Leçon** : bloquer un hash ou une IP gêne peu l'adversaire ; détecter ses **TTP** le force à revoir sa méthode. On priorise donc la détection comportementale.

## Constats
- Le binaire correspond à **Flagpro** (BlackTech) : confirmation via détections VirusTotal et infrastructure associée.
- IoC extraits : hash SHA-256, domaines et IP de commande et contrôle.

## Compétences démontrées
Analyse d'IoC · VirusTotal · hachage SHA-256 · pyramide de la douleur · renseignement sur les menaces (CTI) · priorisation de la détection.
