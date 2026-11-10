# Comment contribuer

La branche `main` est protégée : **personne ne pousse directement dessus**.
Tout changement passe par une branche + une Pull Request (PR) relue par un autre membre.

## Le cycle en 6 étapes

```bash
# 1. Partir d'un main à jour
git checkout main
git pull

# 2. Créer sa branche (une branche = une tâche)
git checkout -b feature/page-contact

# 3. Travailler, puis commiter souvent
git add .
git commit -m "feat: ajoute le formulaire de contact"

# 4. Pousser sa branche
git push -u origin feature/page-contact
```

5. Sur GitHub, cliquer sur **Compare & pull request**, remplir le modèle, demander une relecture.
6. Une fois la PR **approuvée** et **à jour avec main**, cliquer sur **Merge pull request**.
   La branche est supprimée automatiquement. Revenir sur `main` et faire `git pull`.

## Noms de branches

| Préfixe     | Usage                          | Exemple                  |
|-------------|--------------------------------|--------------------------|
| `feature/`  | nouvelle page ou fonctionnalité | `feature/page-accueil`   |
| `fix/`      | correction d'un bug             | `fix/menu-mobile`        |
| `style/`    | CSS / mise en forme uniquement  | `style/couleurs-footer`  |
| `docs/`     | README, documentation           | `docs/consignes`         |

En minuscules, mots séparés par des tirets, sans accents.

## Messages de commit

Format : `type: description courte au présent`

- `feat: ajoute la section équipe`
- `fix: corrige le lien du logo`
- `style: aligne les cartes sur mobile`
- `docs: complète le README`

## Éviter les conflits

- **Faire `git pull` sur main avant de créer une branche.**
- **Des PR petites et fréquentes** : une PR par tâche, mergée vite.
- **Se répartir les fichiers** : éviter que deux personnes modifient le même fichier en même temps
  (ex. une page HTML par personne, un fichier CSS par section si besoin).
- Si GitHub affiche **« This branch is out-of-date »**, cliquer sur **Update branch**.
  En cas de conflit, le résoudre dans sa branche :

```bash
git checkout ma-branche
git pull origin main      # récupère main dans ta branche
# corriger les fichiers marqués en conflit (<<<<<<< ======= >>>>>>>)
git add .
git commit
git push
```

Les conflits se règlent **toujours dans la branche**, jamais sur `main`.
