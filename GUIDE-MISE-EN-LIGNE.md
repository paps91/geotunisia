# Mettre GeoTunisia en ligne : GitHub + Vercel + geotunisia.tn

Pas besoin de savoir programmer. Compter 30 à 45 minutes (hors délai du DNS).

## Étape 1 : créer un compte GitHub
1. Allez sur https://github.com et cliquez sur **Sign up**.
2. Email, mot de passe, nom d'utilisateur ; validez l'email reçu.

## Étape 2 : créer le dépôt (repo)
1. Connecté, cliquez sur **+** (en haut à droite) puis **New repository**.
2. Repository name : `geotunisia`. Laissez **Public** (ou Private, Vercel marche dans les deux cas).
3. Ne cochez rien d'autre (pas de README, pas de .gitignore). Cliquez **Create repository**.

## Étape 3 : envoyer les fichiers
1. Dézippez `geotunisia.zip` sur votre ordinateur : vous obtenez un dossier avec index.html, demographie.html, etc.
2. Sur la page du dépôt vide, cliquez sur le lien **uploading an existing file**.
3. Ouvrez le dossier dézippé, sélectionnez **tout son contenu** (pas le dossier lui-même) et glissez-le dans la page GitHub.
4. Attendez la fin du chargement, puis cliquez **Commit changes** (en bas).
5. Vérifiez que `index.html` est visible à la racine du dépôt (et non dans un sous-dossier).

## Étape 4 : créer le compte Vercel
1. Allez sur https://vercel.com/signup, choisissez **Continue with GitHub** (plan gratuit « Hobby »).
2. Autorisez Vercel à accéder à GitHub.

## Étape 5 : déployer
1. Sur Vercel : **Add New… > Project**.
2. Dans la liste, repérez `geotunisia` et cliquez **Import**.
3. Réglages à ne PAS modifier : Framework Preset = **Other**, Build Command vide, Output Directory vide.
4. Cliquez **Deploy**. Après environ 30 secondes, vous obtenez une adresse du type `geotunisia.vercel.app` : testez le site.

## Étape 6 : brancher geotunisia.tn
1. Projet Vercel > **Settings > Domains** > saisissez `geotunisia.tn` > **Add**.
2. Ajoutez aussi `www.geotunisia.tn` (Vercel proposera de rediriger l'un vers l'autre).
3. Vercel affiche les enregistrements DNS à créer. En général :
   - type **A**, nom `@`, valeur `76.76.21.21`
   - type **CNAME**, nom `www`, valeur `cname.vercel-dns.com`
   (Recopiez les valeurs exactes affichées par Vercel si elles diffèrent.)
4. Allez chez le bureau d'enregistrement du .tn (là où vous avez acheté geotunisia.tn), ouvrez la gestion DNS / zone DNS et créez ces enregistrements.
5. Attendez de quelques minutes à 24 h. Vercel passe alors le domaine en « Valid Configuration » et active le HTTPS tout seul.

## Étape 7 : référencement Google
1. Allez sur https://search.google.com/search-console et ajoutez la propriété `https://geotunisia.tn`.
2. Validez la propriété (méthode DNS : on vous donne un enregistrement TXT à ajouter comme à l'étape 6).
3. Menu **Sitemaps** : saisissez `sitemap.xml` et envoyez.

## Pour modifier le site plus tard
Sur GitHub, ouvrez le fichier, cliquez sur le crayon, modifiez, **Commit changes** : Vercel redéploie automatiquement en une minute.
