# AI RULES (Mood Digital, Astro)

Mission
- Construire des landing pages "world class" (niveau top agences) avec une UX premium.
- Priorité absolue: site ultra fluide, animations propres, sensation haut de gamme.
- Aucune régression: si tu n'es pas sûr, propose une alternative plus safe.

Definition of "World Class"
- Au-dessus de la ligne de flottaison: promesse claire en 2 secondes + preuve + CTA principal visible.
- Hiérarchie visuelle impeccable: 1 message, 1 action, 1 chemin.
- Micro-interactions premium: hover, focus, press, scroll reveal subtil.
- Mobile-first: tout doit être aussi bon sur mobile que sur desktop.
- Copy orientée conversion: concret, court, scannable, sans blabla.

Performance non négociable (qualité perçue)
- Objectif: 60 FPS sur les interactions et animations critiques.
- Pas de layout shift perceptible: CLS proche de 0.
- LCP rapide: éviter images lourdes au-dessus de la ligne de flottaison.
- Ne jamais ajouter de dépendance lourde sans justification.

Règles d'animations (ultra fluide)
- Favoriser uniquement: transform + opacity (GPU-friendly).
- Interdits sauf nécessité: animation de width/height/top/left, box-shadow animé lourd, blur massif en continu.
- Toujours gérer prefers-reduced-motion:
  - Si reduced motion: désactiver ou réduire fortement les animations.
- Easing premium obligatoire: cubic-bezier custom, pas de transitions "linéaires".
- Durées indicatives:
  - micro-interactions: 120-220ms
  - reveals: 500-900ms
- Utiliser des animations "subtiles" qui augmentent la qualité perçue, pas des effets agressifs.

Règles CSS et rendu
- Eviter les effets qui provoquent du repaint constant.
- Utiliser will-change seulement sur l'élément animé, et pas partout.
- Utiliser contain/content-visibility quand pertinent pour les sections hors écran.
- Les hover doivent être nettes et élégantes, pas "cartoon".

Règles Astro (qualité + perf)
- Pas de JS si CSS suffit.
- Hydratation minimale: utiliser les îlots seulement si nécessaire.
- Images:
  - Compresser et servir des tailles adaptées.
  - lazy-load hors hero, et éviter lazy pour l'élément LCP.
- Fonts:
  - éviter trop de variantes
  - précharger si nécessaire

Process obligatoire quand tu modifies du code
1) Plan en 3 étapes (bref).
2) Diff minimal: modifier uniquement les fichiers nécessaires.
3) Vérification:
   - lancer npm run build
   - si build échoue, corriger jusqu'a "Build: OK"

Format de sortie attendu
- Lister les fichiers modifiés.
- Expliquer ce qui change côté UX, perf, et accessibilité.
- Finir par: "Build: OK" ou "Build: FAILED" + cause.

Standard de qualité UI
- Tous les boutons: hover, focus visible, active/press state, disabled state.
- Accessibilité:
  - focus ring visible
  - contrast lisible
- Responsive:
  - pas de texte coupé
  - pas de débordements horizontaux
  - espacements cohérents

Checklist conversion (avant validation)
- H1: bénéfice clair (pas un titre vague)
- Sous-titre: qui, quoi, résultat
- CTA principal: 1 seul, visible, wording action
- 3 preuves rapides: chiffres, logos, résultats, témoignages, avant/après
- 1 section "comment ça marche" en 3 étapes
- 1 section objections: prix, délai, garantie, FAQ
- Footer propre + mentions essentielles
