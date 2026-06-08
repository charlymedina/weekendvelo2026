# 🚴‍♂️ Weekend Vélo 2026 - Roadtrip & Souvenirs

Ce site web statique est le compagnon de route d'un roadtrip vélo multi-jours. Il a été conçu pour servir de portail d'information logistique avant et pendant l'événement pour les participants, puis de se transformer automatiquement en une page de souvenirs épurée pour les proches et suiveurs après la course.

### 🗺️ Itinéraire
Saint-Amand-Montrond ➔ Villefranche-sur-Cher ➔ Tours

---

## 🚀 À quoi sert ce site ?

Le site possède deux modes d'affichage distincts, gérés dynamiquement par JavaScript en fonction de la date actuelle.

### 1️⃣ Mode Actif (Planification & Course)
*Affiché automatiquement jusqu'à la fin de l'événement.*

Ce mode fournit toutes les informations cruciales pour les participants :
*   **Logistique :** Listes de vérification pour les sacoches et les courses (centrées sur l'utilisateur).
*   **Transport :** Itinéraire détaillé du vendredi (trains, dîner, Airbnb).
*   **Suivi Live :** Intégration en temps réel de la localisation via GetCadence.
*   **Parcours prévus :** Cartes interactives Komoot pour le samedi et le dimanche.

### 2️⃣ Mode Souvenir (Après l'événement)
*Affiché automatiquement une fois l'événement terminé.*

Ce mode est une version simplifiée et esthétique pour revivre l'aventure :
*   **Peloton :** La section avec les avatars des participants est conservée.
*   **Résumé épuré :** Pour le samedi et le dimanche, toutes les informations logistiques et cartes de planification disparaissent.
*   **Activités Réalisées :** Seules les publications Strava des activités réelles sont affichées et centrées.
*   **Titres simplifiés :** L'en-tête est mis à jour pour indiquer simplement "Le résumé de notre roadtrip".

---

## 🛠️ Choix Techniques & Documentation

### Structure & Style
*   **Site Statique :** Un seul fichier `index.html` pour une performance et une simplicité d'hébergement maximales (compatible GitHub Pages).
*   **Tailwind CSS (CDN) :** Utilisé pour un design responsive, moderne et un développement rapide.
*   **Design Glassmorphism :** Les blocs de contenu utilisent un effet de verre dépoli (`glass-card`) pour un rendu visuel premium.
*   **Photos Peloton :** Les visages des participants utilisent un masque CSS (`mask-image` et `linear-gradient`) pour un effet de transparence progressive en bas de l'image, évitant l'effet "carré blanc".

### Intégration Strava
Les activités réelles sont affichées via les intégrations officielles Strava. Pour garantir un rendu propre, le conteneur de ces intégrations utilise des classes Flexbox (`flex flex-col items-center`) pour assurer que les résumés Strava sont parfaitement **centrés horizontalement** dans leurs sections respectives.

### Suivi Live (UX)
Pour le suivi live et l'album photos (quand ils étaient actifs), nous avons choisi de ne pas utiliser d'iframes directes, qui sont souvent bloquées par Google/GetCadence pour des raisons de sécurité. L'UX choisie est celle d'un **cadre cliquable total**, agissant comme un bouton géant clignotant. Le clic ouvre le service dans un nouvel onglet, évitant les erreurs de chargement sur le site.

### Automatisation (La Logique de Bascule)
Le cœur de l'automatisation réside dans un script JavaScript à la fin du document.
*   Il gère l'affichage du live via `dateCourseBascule`.
*   Il gère la bascule complète vers la "Vue Souvenirs" via `dateSouvenirsBascule`.
*   Toutes les anciennes sections logistiques et de planification Komoot restent présentes dans le code HTML mais sont masquées, prêtes pour l'année prochaine.

---

## 🔧 Maintenance : Pour l'Année Prochaine

Pour réutiliser ce site l'année prochaine, vous devez mettre à jour les éléments suivants directement dans le script JavaScript à la fin de `index.html` :

1.  **Dates de bascule :**
    *   Mettre à jour `dateCourseBascule` (Ligne ~370) pour le départ de la course.
    *   Mettre à jour `dateSouvenirsBascule` (Ligne ~389) pour la fin de l'événement.
    *   *Rappel : En JavaScript, les mois commencent à 0 (0=janvier, 5=juin, etc.).*
2.  **Photos Peloton :** Remplacer les images dans le dossier `img/` par celles du nouveau peloton (garder les mêmes noms de fichiers simplifiera les choses).
3.  **Strava :** Une fois le weekend terminé, copier-coller les nouveaux codes d'intégration Strava fournis dans les placeholders correspondants dans le `souvenirs-container`.

---

*Développé avec 🚴‍♂️ pour le Peloton Vélo 2026.*
```http://googleusercontent.com/image_generation_content/215
