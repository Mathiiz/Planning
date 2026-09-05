# Guide d'installation et de synchronisation — Planning EDN / ECOS

Ce guide explique pas à pas comment héberger ce tableau de bord gratuitement sur GitHub, l'intégrer directement dans une page Notion et activer la sauvegarde automatique de ta progression sur tous tes appareils.

---

### 1. Créer son compte GitHub et son dossier de projet (Dépôt)

1. Rends-toi sur https://github.com et clique sur « Sign up » pour créer un compte gratuit (ou connecte-toi).
2. Une fois connecté, clique sur le bouton vert « New » (ou sur le symbole « + » en haut à droite > « New repository »).
3. Remplis les champs suivants :
   - Repository name : `planning-edn` (ou le nom de ton choix, sans espace ni accents).
   - Visibilité : Coche impérativement « Public » (obligatoire pour bénéficier de l'hébergement web gratuit avec un compte standard).
   - Coche la case « Add a README file » (cette étape permet d'initialiser immédiatement le dossier pour la mise en ligne).
4. Clique tout en bas sur « Create repository ».

---

### 2. Mettre en ligne le fichier et activer le site web (GitHub Pages)

1. Sur la page de ton dépôt tout juste créé, clique sur le menu « Add file » puis « Upload files ».
2. Prends le fichier HTML de ton planning sur ton ordinateur, assure-toi qu'il est bien renommé en `index.html` (tout en minuscules), puis glisse-le dans la zone centrale.
3. Clique sur le bouton vert « Commit changes » en bas pour valider l'import.
4. Va dans l'onglet « Settings » de ton dépôt (situé dans la barre d'onglets du haut : Code, Issues, Pull requests, ... Settings).
5. Dans la colonne de gauche, clique sur « Pages ».
6. Dans la section « Build and deployment » > « Branch » :
   - Clique sur le menu déroulant qui affiche « None » et sélectionne « main ».
   - Laisse le dossier sur « / (root) ».
   - Clique sur « Save ».
7. Patiente 1 à 2 minutes puis recharge la page. Une bannière verte apparaîtra en haut avec l'adresse de ton site web, sous la forme :
   `https://<ton-pseudo>.github.io/planning-edn/`

---

### 3. Créer une clé d'accès (Token) pour la sauvegarde automatique

Pour que ton planning puisse enregistrer chaque case cochée, jour de repos ou fiche LCA directement dans un fichier `data.json` sur ton compte sans te demander ton mot de passe :

1. Clique sur ta photo de profil tout en haut à droite de GitHub, puis sélectionne « Settings ».
2. Dans le menu de gauche, fais défiler tout en bas et clique sur « Developer settings ».
3. Dans la colonne de gauche, clique sur « Personal access tokens » puis sur « Tokens (classic) ».
4. Clique sur « Generate new token » puis sélectionne « Generate new token (classic) ».
5. Renseigne les options :
   - Note : `Sauvegarde Planning EDN`
   - Expiration : Choisis « No expiration » (ou une durée longue selon ta préférence).
   - Scopes (autorisations) : Coche uniquement la case principale « repo » (Accès complet aux dépôts privés/publics).
6. Fais défiler jusqu'en bas et clique sur « Generate token ».
7. COPIE IMMÉDIATEMENT la série de caractères qui s'affiche et colle-la dans un endroit sûr (Notes, gestionnaire de mot de passe) : elle ne sera plus jamais visible après avoir quitté cette page.

---

### 4. Intégrer le planning dans Notion

1. Ouvre la page Notion où tu souhaites afficher ton tableau de bord.
2. Tape la commande `/intégration` (ou `/embed` si ton Notion est en anglais) et valide avec Entrée.
3. Colle l'adresse web de ton site obtenue à l'étape 2 (`https://<ton-pseudo>.github.io/planning-edn/`).
4. Clique sur « Intégrer le lien » (Embed link).
5. Étire les bords du bloc Notion pour lui donner une largeur et une hauteur confortables.

---

### 5. Finaliser la liaison de sauvegarde

1. Directement depuis ton planning affiché dans Notion (ou depuis ton navigateur), clique sur l'onglet « Paramètres ».
2. Descends jusqu'à la section « Synchronisation GitHub » et saisis tes identifiants :
   - Utilisateur : ton pseudo GitHub (ex: `thomas-dupont`)
   - Dépôt : le nom exact donné à l'étape 1 (ex: `planning-edn`)
   - Fichier de données : laisse `data.json`
   - Branche : laisse `main`
   - Token : colle la clé d'accès générée à l'étape 3 (`ghp_...`)
3. Clique sur « Enregistrer la connexion ».
4. Le statut doit afficher : « Synchronisé ✓ ».

Dès lors, chaque modification effectuée sur ton planning (tâches validées, permutations d'items, fiches LCA, réglages de dates) est automatiquement sauvegardée dans un fichier `data.json` sur ton GitHub et synchronisée sur l'ensemble de tes écrans (ordinateur, tablette, téléphone).
