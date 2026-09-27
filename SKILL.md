---
name: bubble
description: Ouvrir Bubble, une interface visuelle en graphe pour enrichir une idée brute par hypothèses cliquables et lignes validées une à une.
---

# Bubble

Bubble est la version visuelle d'un affinage d'intention. Sur macOS, l'utilisateur peut ouvrir `Bubble.app` dans ce dossier sans passer par le terminal. Depuis Codex, lance l'application locale avec `python3 scripts/bubble.py` dans une session persistante et donne son adresse locale à l'utilisateur. L'interface ouvre normalement le navigateur elle-même. Elle utilise le CLI Codex déjà connecté sur cette machine pour générer les hypothèses ; si ce CLI est indisponible, explique le blocage sans prétendre que les propositions sont dynamiques.

## Fonctionnement

La page affiche l'idée courante comme nœud central et les hypothèses comme nœuds cliquables. Choisir une hypothèse ouvre des lectures ou réponses possibles et redessine le graphe. Une réponse choisie ou rédigée devient immédiatement une ligne candidate, sans appel au modèle. L'utilisateur peut la modifier, la valider telle quelle ou demander une reformulation. Chaque bulle de réponse propose aussi une coche à droite d'« Autres pistes pour celle-ci » pour valider directement sa formulation sans passer par l'écran de modification. Aucune réponse n'entre dans l'intention sans ce clic explicite. Une hypothèse rejetée peut être remplacée ; une branche explorée peut demander d'autres propositions sans modifier les lignes validées.

Le nombre d'hypothèses suit les pistes réellement utiles, sans quota. Chaque bulle reste brève et traite une seule idée, sans menu d'options à l'intérieur. À chaque validation, les nouvelles propositions repartent de l'idée brute et de toutes les lignes validées. Le seuil d'arrêt est un résultat assez clair pour commencer à le réaliser sans inventer l'outcome voulu ; les détails d'exécution restent ouverts. L'interface ne doit pas produire un plan à la place de l'utilisateur.

Le type de réponse est configurable dans Bubble avec un curseur à trois positions : « Simple et clair » par défaut, « Précis et soutenu », ou « Réponses détaillées ». Ce choix s'applique aux prochaines générations et reste enregistré avec la session.

La version conversationnelle d'origine reste dans `../affiner-intention/SKILL.md`. Ne la remplace pas par Bubble.
