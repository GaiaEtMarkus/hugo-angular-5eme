# Guide Hugo pour les Présentations Angular

## 🎯 Objectif

Créer des présentations web modernes et interactives à partir de vos fichiers Markdown pour le cours Angular 20+.

---

## 🚀 Installation et Configuration

### **1. Installation de Hugo**

#### **macOS (recommandé)**
```bash
# Installer via Homebrew
brew install hugo

# Vérifier l'installation
hugo version
```

#### **Windows**
```bash
# Installer via Chocolatey
choco install hugo

# Ou télécharger depuis : https://gohugo.io/installation/windows/
```

#### **Linux**
```bash
# Ubuntu/Debian
sudo apt-get install hugo

# Ou via Snap
sudo snap install hugo --channel=extended
```

### **2. Création du site de présentation**

```bash
# Aller dans le dossier racine du cours
cd "/Users/akramboukhers/Desktop/Angular 5ème année"

# Créer le site Hugo
hugo new site angular-course-presentations

# Aller dans le dossier créé
cd angular-course-presentations
```

### **3. Configuration du thème**

```bash
# Créer un thème personnalisé
hugo new theme angular-course-theme

# Vérifier la structure
ls -la themes/angular-course-theme/
```

---

## ⚙️ Configuration Hugo

### **Fichier de configuration principal (`hugo.toml`)**

```toml
baseURL = 'http://localhost:1313/'
languageCode = 'fr-fr'
title = 'Cours Angular 5ème année'
theme = 'angular-course-theme'

[params]
  description = "Cours complet Angular 20+ pour les étudiants de 5ème année"
  author = "Formateur Angular"

[menu]
  [[menu.main]]
    identifier = "introduction"
    name = "Introduction"
    url = "/introduction/"
    weight = 1
  [[menu.main]]
    identifier = "partie-1"
    name = "Partie 1"
    url = "/partie-1/"
    weight = 2
  [[menu.main]]
    identifier = "partie-2"
    name = "Partie 2"
    url = "/partie-2/"
    weight = 3
  [[menu.main]]
    identifier = "partie-3"
    name = "Partie 3"
    url = "/partie-3/"
    weight = 4
  [[menu.main]]
    identifier = "partie-4"
    name = "Partie 4"
    url = "/partie-4/"
    weight = 5
  [[menu.main]]
    identifier = "partie-5"
    name = "Projet"
    url = "/partie-5/"
    weight = 6

[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
  [markup.highlight]
    style = "github"
    lineNos = true
    lineNumbersInTable = true
```

---

## 🎨 Amélioration de la Lisibilité des Scripts

### **1. Styles CSS personnalisés pour les blocs de code**

Ajoutez ces styles dans le fichier `themes/angular-course-theme/layouts/_default/baseof.html` :

```css
/* Amélioration des blocs de code */
.prose pre {
    background-color: #1f2937;
    color: #f9fafb;
    padding: 1.5rem;
    border-radius: 0.75rem;
    overflow-x: auto;
    margin: 1.5rem 0;
    border: 1px solid #374151;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.prose code {
    background-color: #f3f4f6;
    padding: 0.25rem 0.5rem;
    border-radius: 0.375rem;
    font-size: 0.875rem;
    font-weight: 500;
    color: #1f2937;
    border: 1px solid #d1d5db;
}

/* Numéros de ligne */
.prose pre.line-numbers {
    counter-reset: line;
}

.prose pre.line-numbers > code {
    position: relative;
    padding-left: 3.5rem;
}

.prose pre.line-numbers > code > .line {
    position: relative;
    display: block;
}

.prose pre.line-numbers > code > .line::before {
    counter-increment: line;
    content: counter(line);
    position: absolute;
    left: -3rem;
    width: 2.5rem;
    text-align: right;
    color: #6b7280;
    font-size: 0.75rem;
    padding-right: 0.5rem;
    border-right: 1px solid #374151;
}

/* Amélioration des commentaires */
.prose pre code .comment {
    color: #6b7280;
    font-style: italic;
}

/* Amélioration des commandes */
.prose pre code .command {
    color: #10b981;
    font-weight: 600;
}

/* Amélioration des arguments */
.prose pre code .argument {
    color: #f59e0b;
}

/* Amélioration des chaînes */
.prose pre code .string {
    color: #ef4444;
}
```

### **2. Scripts pour améliorer la lisibilité**

Ajoutez ce script dans le même fichier :

```javascript
// Amélioration de la lisibilité des scripts
document.addEventListener('DOMContentLoaded', function() {
    // Ajouter des classes pour la coloration syntaxique personnalisée
    document.querySelectorAll('pre code').forEach(function(codeBlock) {
        // Ajouter la classe line-numbers
        const pre = codeBlock.parentNode;
        if (pre && !pre.classList.contains('line-numbers')) {
            pre.classList.add('line-numbers');
        }
        
        // Améliorer la coloration des commentaires
        codeBlock.innerHTML = codeBlock.innerHTML.replace(
            /(# .*)/g, 
            '<span class="comment">$1</span>'
        );
        
        // Améliorer la coloration des commandes
        codeBlock.innerHTML = codeBlock.innerHTML.replace(
            /(\b\w+)(?=\s)/g, 
            '<span class="command">$1</span>'
        );
        
        // Améliorer la coloration des arguments
        codeBlock.innerHTML = codeBlock.innerHTML.replace(
            /(--\w+)/g, 
            '<span class="argument">$1</span>'
        );
        
        // Améliorer la coloration des chaînes
        codeBlock.innerHTML = codeBlock.innerHTML.replace(
            /(['"`])(.*?)\1/g, 
            '<span class="string">$1$2$1</span>'
        );
    });
});
```

---

## 🖥️ Commandes Hugo Essentielles

### **1. Commandes de développement**

```bash
# Lancer le serveur de développement
hugo server --buildDrafts

# Lancer avec options avancées
hugo server --buildDrafts --disableFastRender --bind 0.0.0.0

# Lancer avec port personnalisé
hugo server --buildDrafts --port 8080

# Lancer avec ouverture automatique du navigateur
hugo server --buildDrafts --openBrowser
```

### **2. Commandes de build**

```bash
# Build de production
hugo --minify

# Build avec environnement spécifique
hugo --environment production

# Build avec destination personnalisée
hugo --destination ./dist

# Build avec nettoyage
hugo --cleanDestinationDir
```

### **3. Commandes de contenu**

```bash
# Créer une nouvelle page
hugo new content introduction.md

# Créer une page avec archetype
hugo new content posts/mon-article.md

# Créer un nouveau thème
hugo new theme mon-theme

# Lister le contenu
hugo list all
```

### **4. Commandes d'utilitaires**

```bash
# Vérifier la configuration
hugo check

# Vérifier les liens
hugo check --help

# Générer la documentation
hugo gen man

# Générer les métadonnées
hugo gen autocomplete
```

---

## 🌐 Déploiement avec ngrok

### **1. Installation de ngrok**

#### **macOS**
```bash
# Installer via Homebrew
brew install ngrok

# Ou télécharger depuis : https://ngrok.com/download
```

#### **Windows**
```bash
# Installer via Chocolatey
choco install ngrok

# Ou télécharger depuis : https://ngrok.com/download
```

### **2. Configuration de ngrok**

```bash
# Créer un compte sur https://ngrok.com
# Récupérer votre authtoken

# Configurer ngrok avec votre token
ngrok config add-authtoken YOUR_AUTH_TOKEN
```

### **3. Lancement du tunnel**

```bash
# Lancer Hugo en arrière-plan
hugo server --buildDrafts --bind 0.0.0.0 --port 1313 &

# Lancer ngrok pour exposer le port
ngrok http 1313

# Ou avec un domaine personnalisé (version payante)
ngrok http 1313 --subdomain=angular-course
```

### **4. Lancement simple avec ngrok**

```bash
# Lancer Hugo en arrière-plan
hugo server --buildDrafts --bind 0.0.0.0 --port 1313 &

# Lancer ngrok dans un nouveau terminal
ngrok http 1313
```

---

## 📝 Exemples de Contenu Amélioré

### **Exemple de bloc de code avec coloration améliorée**

```markdown
### **Installation de Node.js**

```bash
# Vérifier si Node.js est installé
node --version
npm --version

# Si pas installé, télécharger depuis : https://nodejs.org/
# Ou installer via Homebrew (macOS)
brew install node

# Ou installer via Chocolatey (Windows)
choco install nodejs

# Version requise : Node.js 20+ pour Angular 20+
```

### **Exemple avec étapes numérotées**

```markdown
### **Étapes de configuration**

1. **Installation des dépendances**
   ```bash
   npm install -D tailwindcss@^3.4.0 postcss@^8.4.0 autoprefixer@^10.4.0
   ```

2. **Initialisation de Tailwind**
   ```bash
   npx tailwindcss init
   ```

3. **Configuration PostCSS**
   ```bash
   # Créer postcss.config.js
   echo 'module.exports = { plugins: { tailwindcss: {}, autoprefixer: {} } }' > postcss.config.js
   ```
```

---

## 🔧 Dépannage

### **Problèmes courants**

#### **1. Hugo ne trouve pas le fichier de configuration**
```bash
# Vérifier que vous êtes dans le bon dossier
pwd
ls -la hugo.toml

# Si le fichier n'existe pas, le créer
touch hugo.toml
```

#### **2. Erreur de port déjà utilisé**
```bash
# Vérifier les processus sur le port 1313
lsof -i :1313

# Tuer le processus
kill -9 <PID>

# Ou utiliser un autre port
hugo server --port 8080
```

#### **3. ngrok ne fonctionne pas**
```bash
# Vérifier la configuration
ngrok config check

# Vérifier l'authtoken
ngrok config add-authtoken YOUR_TOKEN

# Redémarrer ngrok
pkill ngrok
ngrok http 1313
```

---

## 📚 Ressources utiles

- [Documentation officielle Hugo](https://gohugo.io/documentation/)
- [Thèmes Hugo](https://themes.gohugo.io/)
- [ngrok Documentation](https://ngrok.com/docs)
- [Markdown Guide](https://www.markdownguide.org/)

---

## 🎯 Workflow recommandé

1. **Développement local** : `hugo server --buildDrafts`
2. **Test avec ngrok** : `ngrok http 1313`
3. **Build de production** : `hugo --minify`
4. **Déploiement** : Upload du dossier `public/`

**Bonne présentation !** 🎉
