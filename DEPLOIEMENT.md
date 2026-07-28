# Déploiement · Suivi D-TECH Fuites & Hydrosolutions

Convention identique au dashboard BMW Motorrad (compte `emichel-blip`).

## Cible proposée

- **Repo** : `dtech-fuites-suivi`
- **URL Pages** : https://emichel-blip.github.io/dtech-fuites-suivi/
- **URL édition Empirik** : https://emichel-blip.github.io/dtech-fuites-suivi/#admin
- **URL client (option Cloudflare Access)** : https://suivi-dtech.empirik.fr

## Étape 1 — Créer le repo et pousser

Dans le Terminal, depuis le dossier du projet :

```bash
cd "~/Tools/Dtech Fuites - Avancement projet"
git init
git add index.html README.md DEPLOIEMENT.md .gitignore
git commit -m "init: suivi production D-TECH Fuites & Hydrosolutions"
git branch -M main
gh repo create dtech-fuites-suivi --public --source=. --remote=origin --push
```

Si tu préfères sans `gh` :

```bash
git remote add origin https://github.com/emichel-blip/dtech-fuites-suivi.git
git push -u origin main
```

## Étape 2 — Activer GitHub Pages

Repo GitHub → **Settings** → **Pages** → Source : `main` / `/ (root)` → Save.
L'URL `https://emichel-blip.github.io/dtech-fuites-suivi/` est active en 2 à 5 min.

## Étape 3 — Publication en un clic (token GitHub fine-grained)

Pour activer le bouton **Publier sur GitHub** depuis le dashboard :

1. https://github.com/settings/personal-access-tokens/new
2. **Repository access** → **Only select repositories** → `dtech-fuites-suivi`
3. **Permissions** → **Contents** : **Read and write** (le reste sur No access)
4. **Generate token** → copier `github_pat_...`
5. Dans le dashboard (mode `#admin`) : **Publier** → coller le token → **Enregistrer**
6. Ensuite, **Publier sur GitHub** commit et push automatiquement, Pages rebuild en ~1 min.

Le token reste uniquement dans le localStorage du navigateur (jamais committé).

## Étape 4 (option) — Domaine + Cloudflare Access

Pour réserver l'accès (email magique) et un joli domaine :

1. Cloudflare DNS de `empirik.fr` : CNAME `suivi-dtech` → `emichel-blip.github.io` (proxifié).
2. GitHub → Settings → Pages → **Custom domain** : `suivi-dtech.empirik.fr` + Enforce HTTPS.
3. Cloudflare Zero Trust → Access → Applications → Self-hosted → domaine `suivi-dtech.empirik.fr` → policy Allow sur les emails autorisés (client + `@empirik.fr`).

Tant que le domaine n'est pas protégé, l'URL Pages brute est publique. En attendant, ne communiquer que l'URL nécessaire, ou activer une porte d'entrée.

## Mettre à jour le suivi

1. Ouvrir l'URL `#admin`.
2. Cocher / saisir l'avancement.
3. **Publier** → **Publier sur GitHub**.

Le client voit la mise à jour sur son URL en ~1 min.
