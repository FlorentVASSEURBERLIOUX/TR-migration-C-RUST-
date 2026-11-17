# Tremplin Recherche : Migration Incrémentale C vers Rust

## Contexte & Objectifs
Ce projet est mené dans le cadre du programme Tremplin Recherche (ESIEE Paris). Il vise à évaluer expérimentalement les effets d'une migration incrémentale de composants C vers Rust sur la sécurité mémoire et les performances d'un système hybride.
L'attention est particulièrement portée sur la frontière entre les deux langages (interfaces FFI) et l'utilisation de code `unsafe`.

## Méthodologie
1. **Baseline C :** Évaluation des performances et des failles d'un composant C existant.
2. **Architecture Hybride :** Remplacement progressif par des modules Rust via des interfaces FFI.
3. **Vérification :** Fuzzing (AFL++, cargo-fuzz) et analyse mémoire (AddressSanitizer, Miri).
4. **Performances :** Profilage de l'overhead lié aux conversions de types à la frontière FFI.

## Structure du dépôt
- `src/c/` : Implémentation d'origine en C et points d'entrée FFI.
- `src/rust/` : Composants réécrits en Rust.
- `analyses/` : Rapports de benchmarks et de fuzzing.
- `doc/` : État de l'art et rapports de recherche.