### Mini Tutoriel de GitHub Flow

Dans ce tutoriel, je vais vous guider à travers le flux de travail de GitHub en utilisant des commandes Git. Ce flux inclut la création de branches basées sur des tâches Jira, la création de pull requests, la révision et la fusion des changements.

#### Prérequis

1. **Compte GitHub** : Assurez-vous d'avoir un compte GitHub.
2. **Dépôt** : Assurez-vous d'avoir accès au dépôt sur lequel vous allez travailler.
3. **Git installé** : Assurez-vous d'avoir Git installé sur votre machine.

#### Étape 1 : Créer une Branche pour la Tâche

1. **Cloner le dépôt** (si ce n'est pas déjà fait) :
   ```bash
   git clone https://github.com/votre-utilisateur/votre-depot.git
   cd votre-depot
   ```

2. **Créer une nouvelle branche basée sur la tâche Jira** :
   ```bash
   git checkout -b KAN-163
   ```

#### Étape 2 : Réaliser des Changements

1. **Faire des changements dans votre branche** :
   ```bash
   # Modifiez les fichiers nécessaires
   ```

2. **Valider les changements** :
   ```bash
   git add .
   git commit -m "Description des changements effectués"
   ```

3. **Pousser les changements vers GitHub** :
   ```bash
   git push origin KAN-163
   ```

#### Étape 3 : Créer une Pull Request

1. **Aller au dépôt sur GitHub**.
2. **Créer une Pull Request** depuis la branche `KAN-163` vers la branche `develop`.
3. **Assigner Jesús León comme réviseur**.

#### Étape 4 : Révision et Fusion

1. **Attendre la révision de Jesús León**.
2. **Une fois la Pull Request approuvée**, fusionner la branche `KAN-163` avec `develop`.

#### Étape 5 : Supprimer la Branche

1. **Supprimer la branche locale** :
   ```bash
   git checkout develop
   git branch -d KAN-163
   ```

2. **Supprimer la branche distante** :
   ```bash
   git push origin --delete KAN-163
   ```

#### Gestion des Hotfixes

1. **Créer une branche de hotfix à partir de `master`** :
   ```bash
   git checkout master
   git checkout -b hotfix-KAN-163
   ```

2. **Réaliser les changements nécessaires** :
   ```bash
   # Modifiez les fichiers nécessaires
   ```

3. **Valider les changements** :
   ```bash
   git add .
   git commit -m "Description du hotfix"
   ```

4. **Pousser les changements vers GitHub** :
   ```bash
   git push origin hotfix-KAN-163
   ```

5. **Créer une Pull Request** depuis la branche `hotfix-KAN-163` vers la branche `master`.
6. **Assigner Jesús León comme réviseur**.

7. **Une fois la Pull Request approuvée**, fusionner la branche `hotfix-KAN-163` avec `master`.

8. **Fusionner le hotfix avec `develop`** :
   ```bash
   git checkout develop
   git merge hotfix-KAN-163
   git push origin develop
   ```

9. **Supprimer la branche de hotfix** :
   ```bash
   git branch -d hotfix-KAN-163
   git push origin --delete hotfix-KAN-163
   ```

### Conclusion

Ce flux de travail assure que les changements soient révisés et approuvés avant d'être fusionnés avec la branche `develop` ou `master`. De plus, il garantit que les hotfixes soient intégrés à la fois dans `master` et `develop` pour maintenir la cohérence du projet.