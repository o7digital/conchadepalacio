# Mémoire technique — Concha de Palacio

Dernière mise à jour : 3 septembre 2026

## État en production

- Projet : `olivier-steineur/conchadepalacio`
- Branche : `main`
- Dernier commit déployé : `7f51849` — `Lighten contact background overlay`
- Domaine de production : https://interiores.conchadepalacio.com/
- Déploiement Vercel : production prête, aliasée sur `conchadepalacio.vercel.app`
- DNS GoDaddy : le sous-domaine `interiores.conchadepalacio.com` est déjà configuré et fonctionne. Ne pas modifier le DNS.

## Fonctionnalités déjà terminées

- Formulaire de contact Formspree : `https://formspree.io/f/xjyvovdr`
- Email partout : `contact@conchadepalacio.com`
- Téléphone partout : `+1 619 707 1357` (lien `tel:+16197071357`)
- Avis de confidentialité espagnol puis anglais : Mexique, RGPD, Californie et cookies
- Société : LIC International Inc., 1515 Plume Grass Pl, Round Rock, TX 78655 US, EIN 74-2903110
- Menu latéral : `San Diego, California`
- Pied de page : `San Diego, California · Proyectos internacionales`
- Navigation du pied de page ajoutée
- Modal d’avis de confidentialité fonctionnelle
- Header renforcé : logo, ES/EN, Contact et menu plus lisibles
- Voile de la section Contact allégé pour mieux voir la photo

## SEO à reprendre — corrections 1 à 5 demandées

Les corrections suivantes ont été préparées localement mais ne sont pas encore commitées ni déployées :

1. Remplacer les URLs SEO `conchadepalacio.com` par `interiores.conchadepalacio.com` dans canonical, Open Graph, sitemap, robots et données structurées.
2. Sortir les images base64 du HTML pour réduire le poids initial (HTML actuel environ 3,28 Mo).
3. Utiliser réellement les routes/pages Astro ; actuellement le contenu principal est encore dans `public/index.html`.
4. Ajouter des images responsives avec `srcset`, `sizes`, dimensions et chargement différé.
5. Créer des routes espagnole et anglaise séparées (`/es/` et `/en/`) avec `hreflang`.

## Fichiers locaux préparés à vérifier

- `scripts/migrate-seo.mjs`
- `src/content/site.es.html`
- `src/content/site.en.html`
- `src/styles/site.css`
- `public/scripts/site.js`
- `public/images/`

Ces fichiers ont été générés pour la migration SEO, mais il faut encore les intégrer proprement dans Astro, vérifier le rendu, puis seulement commit/push/déployer.

## Commandes utiles

```bash
npm run build
astro dev --background
astro dev status
astro dev logs
astro dev stop
git status
git log -1 --oneline
npx vercel --prod --yes
```

## Attention

- Ne pas modifier le DNS GoDaddy : il est déjà opérationnel.
- Ne pas déployer la migration SEO sans vérifier `/es/`, `/en/`, le formulaire, le menu, la modal de confidentialité et les images.
- Le contenu actuel est dans `public/index.html`, avec beaucoup d’images inline en base64.
