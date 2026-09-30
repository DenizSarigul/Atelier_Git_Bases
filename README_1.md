# Atelier Git – Les bases

Cet atelier sert à mettre en place votre environnement de travail (**GitHub Codespaces**) et à utiliser pour la première fois les commandes **Git**.

**Objectif final :** créer un fichier `fichier1.txt`, l'enregistrer avec Git (*commit*) puis l'envoyer sur GitHub (*push*).

---

## Prérequis

- Un navigateur web récent (Chrome, Firefox, Edge…)
- Une adresse e-mail valide pour créer un compte GitHub

Vous n'avez **rien à installer** sur votre machine : Codespaces fournit un environnement Linux en ligne, avec Git déjà installé.

---

## Étape 1 – Créer un compte GitHub

1. Rendez-vous sur [https://github.com](https://github.com).
2. Cliquez sur **Sign up** et suivez les instructions.
3. Validez votre adresse e-mail.

> Si vous avez déjà un compte GitHub, passez directement à l'étape 2.

---

## Étape 2 – Forker le repository de l'atelier

Un *fork* est une copie d'un repository dans votre propre compte GitHub. Vous pourrez y travailler librement, sans modifier le repository d'origine.

1. Une fois connecté, rendez-vous sur le repository de l'atelier : [https://github.com/bstocker/Atelier_Git_Bases](https://github.com/bstocker/Atelier_Git_Bases).
2. Cliquez sur le bouton **Fork** (en haut à droite).
3. Laissez votre compte comme **Owner** et le nom du repository inchangé.
4. Cliquez sur **Create fork**.

Vous êtes maintenant sur **votre copie** du repository (l'adresse est de la forme `https://github.com/<votre-pseudo>/Atelier_Git_Bases`).

> ⚠️ Pour la suite de l'atelier, travaillez toujours depuis **votre fork**, et non depuis le repository d'origine.

---

## Étape 3 – Lancer un Codespace

1. Sur la page de **votre fork**, cliquez sur le bouton vert **Code**.
2. Sélectionnez l'onglet **Codespaces**.
3. Cliquez sur **Create codespace on main**.

Patientez quelques instants : un éditeur VS Code s'ouvre dans votre navigateur.

---

## Étape 4 – Ouvrir le terminal

Le terminal se trouve normalement en bas de l'écran. S'il n'est pas visible :

- Menu **☰** → **Terminal** → **New Terminal**
- ou raccourci clavier : `Ctrl` + `` ` ``

Vérifiez que Git est bien présent sur la machine (le *host*) :

```bash
git --version
```

Vous devez voir s'afficher une ligne du type `git version 2.x.x`.

---

## Étape 5 – Créer un premier fichier

Créez un fichier vide :

```bash
touch fichier1.txt
```

Écrivez une phrase dedans :

```bash
echo "Hello World !" > fichier1.txt
```

Affichez son contenu pour vérifier :

```bash
cat fichier1.txt
```

Vous devez voir : `Hello World !`

---

## Étape 6 – Vérification de la part de Git

Demandez à Git l'état de votre répertoire :

```bash
git status
```

Git vous indique que `fichier1.txt` est un fichier **non suivi** (*Untracked files*, en rouge) : il existe, mais Git ne le sauvegarde pas encore.

---

## Étape 7 – Ajouter le fichier à la sauvegarde (`git add`)

La commande suivante prend **tout le contenu du répertoire** et le prépare pour la prochaine sauvegarde :

```bash
git add .
```

> 💡 Avec Git, vous pouvez être très fin dans le choix des fichiers à sauvegarder. Par exemple, `git add *.txt` n'ajoute que les fichiers `.txt`, et `git add fichier1.txt` n'ajoute que ce fichier.

Vérifiez à nouveau l'état :

```bash
git status
```

Cette fois, `fichier1.txt` apparaît en **vert** dans *Changes to be committed* : il est prêt à être enregistré.

---

## Étape 8 – Enregistrer la sauvegarde (`git commit`)

Un *commit* est une photo de votre projet à un instant donné, accompagnée d'un message qui décrit la modification :

```bash
git commit -m "Initialisation du projet"
```

| Élément                         | Signification                                              |
|---------------------------------|------------------------------------------------------------|
| `git commit`                    | Enregistre les fichiers ajoutés avec `git add`             |
| `-m "Initialisation du projet"` | Le message qui décrit ce commit (obligatoire)              |

> ℹ️ À ce stade, la sauvegarde existe **uniquement dans votre Codespace**. Elle n'est pas encore visible sur GitHub.

---

## Étape 9 – Envoyer le commit sur GitHub (`git push`)

Envoyez votre commit vers votre fork sur GitHub :

```bash
git push origin main
```

| Élément    | Signification                                                   |
|------------|-----------------------------------------------------------------|
| `git push` | Envoie vos commits locaux vers le repository distant            |
| `origin`   | Le nom du repository distant (ici, votre fork sur GitHub)       |
| `main`     | La branche à envoyer                                            |

Rafraîchissez la page de votre fork sur GitHub : `fichier1.txt` doit apparaître dans la liste des fichiers, avec le message **« Initialisation du projet »**.

---

## ✅ Travail demandé

Faites le `git push` de l'étape 9 pour que `fichier1.txt` soit présent dans **votre fork** sur GitHub. Votre enseignant vérifiera sa présence.

---

> ⚠️ Pensez à **arrêter votre Codespace** quand vous avez terminé (bouton vert **Code** → onglet **Codespaces** → **…** → **Stop codespace**) afin de ne pas consommer inutilement votre quota d'heures gratuites.
