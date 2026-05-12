# Fiche de veille — Claude Code « Agent View »

> Source : transcription d'une vidéo YouTube (tutoriel / annonce de fonctionnalité).
> Date de traitement : 2026-05-12.

## Metadata
- **Sujet principal** : nouvelle fonctionnalité « Agent View » de Claude Code (CLI) — vue unique pour piloter plusieurs agents Claude Code en parallèle ; mention connexe de la commande `/goal`.
- **Pertinence** : **haute** — touche directement à l'usage productif de Claude Code à grande échelle (orchestration multi-agents), pertinent pour des missions de conseil et de formation IA.

## Resume executif (5 lignes max)
Claude Code introduit « Agent View » : un seul onglet de terminal pour visualiser et naviguer entre toutes ses sessions/agents en cours, voir leur statut (en cours, terminé, en attente d'input), entrer/sortir d'une session et même en lancer de nouvelles. On y accède via la flèche gauche dans n'importe quelle session, ou `claude agents` / `claude --bg "<tâche>"` / `/bg`. La fonctionnalité est en *research preview* (donc bugs possibles, ralentissements observés). Le présentateur évoque aussi `/goal` (boucle d'optimisation type « Ralph Wiggum » / auto-research à la Karpathy) qui peut tourner des heures vers un objectif. Message de fond : utiliser le CLI plutôt que l'extension VS Code, et traiter Claude Code comme un « OS » multi-agents.

## Points cles (max 7)
- **Agent View = vue d'orchestration** : tous les agents dans un onglet, sélection au clavier (flèches) ou souris, statut couleur (vert = terminé, jaune = attend un input).
- **Navigation** : flèche gauche pour ouvrir l'Agent View depuis une session ; flèche droite pour entrer dans une session ; flèche gauche pour revenir.
- **Lancer des agents** : taper directement une tâche dans l'Agent View crée une nouvelle session ; sinon `claude agents`, `claude --bg "tâche"` (guillemets obligatoires, pas de crochets), ou `/bg` depuis une session active.
- **Gestion des sessions** : répondre à une demande d'input directement depuis la vue (barre espace), tuer une session avec `Ctrl+X` deux fois, voir la durée d'exécution de chaque session à droite.
- **Cas d'usage cités par l'équipe** : (1) monter en charge sur le nombre de sessions concurrentes, (2) gérer des agents longue durée, (3+4) exploiter la nouvelle commande `/goal`.
- **`/goal`** : on fixe un objectif, Claude Code itère/expérimente jusqu'à l'atteindre — peut tourner des heures voire la nuit ; fonctionne beaucoup mieux avec une métrique objective qu'avec un prompt vague.
- **Statut & limites** : *research preview* — bugs attendus, ralentissement machine constaté au lancement ; multi-répertoires possible mais le répertoire courant n'est pas affiché clairement dans la vue.

## Ce qui est nouveau ou surprenant
- Claude Code se rapproche d'un **gestionnaire d'agents façon « tableau de bord »** dans le terminal, sans dépendre de plusieurs onglets ni de hooks de notification bricolés.
- On peut **spawner une session juste en écrivant un prompt dans la vue** — friction quasi nulle pour paralléliser.
- **`/goal`** (équivalent du « goal » de Codex / boucle agentique persistante) — déplacement vers de l'**auto-research orienté métrique** exécuté en arrière-plan sur de longues durées.
- Petit recap de fin de session de terminal (rappel de ce sur quoi on travaillait) déjà ajouté en amont — détail UX utile.
- Le présentateur insiste : **le CLI a plus de fonctionnalités que l'extension VS Code** — l'extension reste en retard sur les nouveautés.

## Applications concretes pour un MCF qui fait du consulting IA
- **Démo / formation** : excellent support pour montrer en atelier comment orchestrer plusieurs agents IA en parallèle (gain de productivité tangible, visuel immédiat).
- **Méthodo « agent comme OS »** : intégrer dans un cours/conseil le pattern « 1 vue, N agents longue durée », avec règles de bonne pratique (nommer les tâches, isoler par répertoire/projet).
- **Cadrage des attentes client** : rappeler que c'est en *research preview* → ne pas le mettre en prod critique tel quel ; prévoir un plan de fallback (onglets terminaux + hooks de notification).
- **Prompting pour `/goal`** : transposer la culture « optimiser une métrique » (auto-research type Karpathy) — utile pour des POC où l'on définit un critère d'arrêt mesurable plutôt qu'un livrable flou.
- **Recommandation outillage** : pousser les équipes accompagnées vers le CLI plutôt que l'extension VS Code pour bénéficier des dernières capacités.
- **Veille concurrentielle** : comparer avec le « goal » de Codex / autres frameworks d'orchestration multi-agents pour un benchmark client.

## A creuser (liens, refs, outils mentionnes)
- **Doc officielle « Agent View »** de Claude Code (annoncée « dropped today » dans la vidéo) — à retrouver sur la doc Anthropic / Claude Code.
- Commandes à tester : `claude agents`, `claude --bg "<tâche>"`, `/bg`, `/goal`, `Ctrl+X` ×2 (kill), barre espace (répondre depuis la vue).
- **`/goal` dans Codex** — comparer le comportement (boucle « Ralph Wiggum »).
- **« Auto-research » à la Karpathy** — référence de prompting orienté optimisation de métrique.
- **Extension VS Code Claude Code** vs CLI — vérifier l'écart de fonctionnalités à date.
- Cours « build your own AI OS with Claude Code » mentionné par l'auteur (~2 h 30) — source secondaire, à identifier si pertinent pour de la formation.
- Hooks de notification Claude Code (fin de session) — à documenter comme complément/fallback à l'Agent View.

---
*Limite de la source : transcription auto d'une vidéo promotionnelle d'un créateur de contenu (termes parfois mal retranscrits : « Cloud Code » = Claude Code, « Codeex » = Codex, « clawed » = Claude, « SLG goal » = `/goal`). À recouper avec la documentation officielle avant diffusion client.*
