[LISEZ-MOI.md](https://github.com/user-attachments/files/33846401/LISEZ-MOI.md)
# Medibio Inventory — version Android (Redmi Note 8)

Ce dossier contient deux façons d'installer l'application sur votre téléphone.

## Option A — PWA (la plus rapide, aucun outil à installer)
Dossier : `pwa/`

1. Mettez le contenu du dossier `pwa/` en ligne sur un hébergement HTTPS gratuit :
   - **Netlify Drop** : allez sur https://app.netlify.com/drop et glissez-déposez le dossier `pwa`.
   - ou GitHub Pages / Cloudflare Pages.
2. Sur le Redmi, ouvrez l'adresse obtenue avec **Chrome**.
3. Menu ⋮ → **Installer l'application** (ou « Ajouter à l'écran d'accueil »).
4. L'icône Medibio apparaît dans vos applications ; elle s'ouvre en plein écran et fonctionne **hors ligne** après la première ouverture.

## Option B — Vrai fichier APK
Dossier : `android/` (projet Android Studio, code Java).

### B1. Sans installer Android Studio (GitHub Actions)
1. Créez un dépôt GitHub (privé si vous voulez) et envoyez-y **le contenu** du dossier `android/` (le dossier `.github` doit être à la racine du dépôt).
2. Onglet **Actions** → « Build APK » → attendez la fin (≈ 3-5 min).
3. Téléchargez l'artefact **MedibioInventory-apk** (zip contenant `app-debug.apk`).
4. Copiez l'APK sur le téléphone, ouvrez-le et autorisez « Installer des applications inconnues » pour votre gestionnaire de fichiers.

### B2. Avec Android Studio
1. Ouvrez le dossier `android/` dans Android Studio, attendez la synchronisation Gradle.
2. Menu **Build → Build APK(s)**.
3. L'APK est dans `app/build/outputs/apk/debug/app-debug.apk`.

## Ce qui est géré dans la version APK
- Toutes les données restent dans le stockage local de l'appli (comme dans le navigateur).
- **Exports Excel / CSV / JSON** : enregistrés dans le dossier *Téléchargements* du téléphone.
- **Envoyer par mail** : ouvre le menu de partage Android avec le fichier en pièce jointe.
- **Imprimer / PDF** : utilise l'impression Android (choisir « Enregistrer au format PDF »).
- **Import de fichiers** (articles, stock, sauvegarde JSON) : sélecteur de fichiers Android.
- Boutons « Annuler / OK » des confirmations (suppressions, etc.) pris en charge.

## Important
- **Les données sont liées à l'appli** : désinstaller l'APK (ou vider ses données) les efface. Faites régulièrement une sauvegarde via *Export JSON*.
- Si vous utilisez à la fois la PWA et l'APK, leurs données sont **séparées** : transférez-les avec Export JSON / Import JSON.
- Le projet Android et le HTML modifié n'ont pas pu être compilés/testés dans mon environnement (pas de SDK Android) : si le build échoue, envoyez-moi le message d'erreur.
