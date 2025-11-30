# Ecosystem Simulator - Version conforme au libellé du devoir

Ce projet implémente l'ensemble des exigences du devoir pratique :
- Architecture POO (namespaces, classes, structs)
- Gestion mémoire (std::unique_ptr, destructeurs, RAII pour SDL)
- Simulation de base (énergie, faim, reproduction, mouvement)
- Rendu SDL3 (fenêtre, renderer, primitives graphiques)
- Gestion d'événements (ESPACE, R, F, flèches, ESC)
- Chaîne alimentaire (herbivores mangent plantes, carnivores mangent herbivores)
- Comportements intelligents simples (recherche de nourriture, fuite/chasse)
- Statistiques (console + CSV `stats_*.csv`)
- Équilibrage par paramètres dans `SimulationParams`

## Compilation rapide

### Avec g++
g++ -std=c++17 -Iinclude -o ecosystem src/main.cpp src/Core/Entity.cpp src/Core/Ecosystem.cpp src/Graphics/Window.cpp src/Graphics/Renderer.cpp -lSDL3 -pthread

### Avec CMake
mkdir build && cd build
cmake ..
make
./ecosystem

## Contrôles
- ESPACE : pause / resume
- R : reset simulation
- F : ajouter une plante
- FLÈCHE HAUT / BAS : augmenter / diminuer vitesse de simulation
- ÉCHAP : quitter

## Fichiers notables
- `include/` : headers
- `src/` : implémentations
- `stats_YYYYMMDD_HHMMSS.csv` : CSV de statistiques généré automatiquement dans le dossier d'exécution.

## Limitations / Notes
- Rendu simple (cercles) pour se concentrer sur la logique
- Pas d'utilisation de SDL_ttf pour afficher du texte (console + CSV suffisent)
- Comportements heuristiques simples mais crédibles
