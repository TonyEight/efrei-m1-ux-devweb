# Chantiers en cours - version 2026-2027

Liste de travail de la refonte, tenue à jour au fil des commits. Les éléments terminés sont retirés plutôt que barrés. Le détail de la structure cible du support est dans `docs/plan-support-2026-2027.md`.

## Support de cours (`support/index.html`)

- [ ] Chapitre 5 : ajouter l'encadré container queries (5.3), `loading="lazy"` (5.7) et la nouvelle section 5.8 details / summary.
- [ ] Chapitre 7 (nouveau) : web responsable, accessibilité et éco-conception, protocole d'audit. Absorbe l'actuel chapitre 9.
- [ ] Chapitre 8 (nouveau) : projet fil rouge landing page, en remplacement du CV. Reprendre l'énoncé de `exercices/landing-page/README.md`.
- [ ] Chapitre 9 : refonte IA (paysage par usage, tableau daté septembre 2026).
- [ ] Chapitre 10, bibliographie et récapitulatif : actualisations légères prévues au plan du support.
- [ ] Renuméroter le sommaire de la sidebar et les ancres une fois les chapitres 7 à 9 en place.
- [ ] Exemple 6.11 : le bouton primaire utilise `color: #ffffff` en dur, ce qui donne un contraste d'environ 3:1 sur `#4d94ff` en mode sombre. Passer en `color: var(--couleur-fond)` comme dans le kit de patterns, pour que le support reste exemplaire sur ce qu'il enseigne.
- [ ] Section 4.2 : retirer "ce que vous avez vécu en cours" (référence à la promotion précédente) au profit d'un cas générique Safari et Chrome.
- [ ] Régénérer le PDF après la refonte et le renommer en 2026-2027 ; mettre à jour le lien de la topbar (ligne `id="pdfBtn"`), qui pointe encore vers `EFREI_M1_UX_Développement_Web_2026.pdf`.

## Hors périmètre, à ne pas toucher

- La branche `archive/2025-2026` et le tag `2025-2026` sont figés.
- L'ancien repo `efrei-m1-ux-devweb-2025-2026` reste en archive.
