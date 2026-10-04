# Réponse à un incident d'hameçonnage (phishing)

> Analyse d'un courriel d'hameçonnage ciblé et application d'un playbook de réponse à incident.

## Contexte
Un courriel suspect est signalé. En tant qu'analyste SOC, j'investigue le message, j'évalue la menace, puis j'applique le **playbook** de réponse approprié (ticket A-2703).

## Analyse du courriel
1. **En-têtes** : vérification de l'expéditeur réel, du chemin `Received`, des alignements SPF/DKIM/DMARC.
2. **Contenu** : ton d'urgence, prétexte, incohérences ; usurpation d'une marque de confiance.
3. **Lien / pièce jointe** : l'URL mène à un **faux formulaire de connexion** (vol d'identifiants) hébergé sur un domaine ressemblant.

## Constats
- Courriel d'**hameçonnage ciblé** (spear phishing) cherchant à récolter des identifiants.
- Indicateurs : domaine look-alike, formulaire de connexion malveillant, lien raccourci.

## Réponse (playbook)
| Étape | Action |
|---|---|
| Triage | Classer l'alerte, confirmer qu'il s'agit d'un phishing. |
| Confinement | Mettre le message en quarantaine, bloquer l'URL/domaine et l'expéditeur. |
| Investigation | Chercher d'autres destinataires, vérifier si des identifiants ont été saisis. |
| Éradication | Supprimer le message des boîtes, invalider les sessions/mots de passe si compromission. |
| **Escalade** | Escalader au niveau 2 **avec les preuves techniques** (en-têtes, URL, capture du formulaire). |
| Récupération & leçons | Réinitialiser les comptes touchés, sensibiliser les utilisateurs. |

## Compétences démontrées
Investigation SOC · analyse d'en-têtes de courriel · détection d'hameçonnage · application d'un playbook · escalade documentée par preuves.
