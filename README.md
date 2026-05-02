# 🍕 LAB 6 — Application PizzaRecipes
### Développement Mobile Android — Java

---
<img width="371" height="684" alt="demo_compressed" src="https://github.com/user-attachments/assets/85e0f4c9-e835-474b-b788-54a95ee055e7" />


## 📋 Description

Application Android développée en Java qui affiche une liste de 10 recettes de pizzas avec leurs informations (nom, prix, durée, image), et permet d'accéder à la fiche détaillée de chaque recette (ingrédients, description, étapes de préparation).

---

## 🏗️ Structure du projet

```
com.example.pizzarecipes/
│
├── Produit.java              → Modèle de données (entité Pizza)
├── IDao.java                 → Interface générique CRUD (DAO)
├── ProduitService.java       → Singleton + données en mémoire (10 pizzas)
├── PizzaAdapter.java         → Adapter personnalisé pour la ListView
├── SplashActivity.java       → Écran de démarrage (2 secondes)
├── ListPizzaActivity.java    → Liste des pizzas
└── PizzaDetailActivity.java  → Détail complet d'une pizza
```

---

## 📱 Écrans de l'application

### 1. Splash Screen
- Affiche le logo (pizza1) et le titre pendant **2 secondes**
- Utilise un `Thread` avec `Thread.sleep(2000)`
- Redirige automatiquement vers la liste

### 2. Liste des Pizzas
- Affiche les 10 pizzas dans une `ListView`
- Chaque ligne montre : image, nom, durée et prix
- Un clic sur une pizza ouvre sa fiche détaillée

### 3. Détail d'une Pizza
- Affiche l'image en grand
- Nom, durée, prix
- Ingrédients complets
- Description
- Étapes de préparation numérotées

---

## 🧱 Concepts mis en œuvre

| Concept | Fichier |
|---|---|
| Modèle orienté objet + AUTO_ID | `Produit.java` |
| Pattern DAO générique | `IDao.java` |
| Singleton + seed() | `ProduitService.java` |
| BaseAdapter personnalisé | `PizzaAdapter.java` |
| Splash Screen avec Thread | `SplashActivity.java` |
| ListView + setOnItemClickListener | `ListPizzaActivity.java` |
| Intent + putExtra / getLongExtra | `ListPizzaActivity` → `PizzaDetailActivity` |
| ScrollView pour le détail | `activity_pizza_detail.xml` |

---

## ⚙️ Configuration

| Paramètre | Valeur |
|---|---|
| Nom du projet | PizzaRecipes |
| Package | com.example.pizzarecipes |
| Langage | Java |
| Minimum SDK | API 24 (Android 7.0) |
| Target SDK | API 34 |

---

## 🖼️ Images

Les images `pizza1.jpg` à `pizza10.jpg` doivent être placées dans :
```
app/src/main/res/drawable/
```
Elles sont référencées dans le code via `R.drawable.pizza1`, `R.drawable.pizza2`, etc.

> Source des images : fournies par le professeur dans le dossier `Ressources/TP/images`

---

## 🚀 Installation et lancement

1. Ouvrir **Android Studio**
2. **File → Open** → sélectionner le dossier du projet
3. Copier les images `pizza1.jpg` → `pizza10.jpg` dans `res/drawable/`
4. **File → Sync Project with Gradle Files**
5. **Build → Clean Project**
6. **Run → Run 'app'** (ou Shift+F10)

---

## 🔄 Flux de navigation

```
SplashActivity
     │  (après 2 secondes)
     ▼
ListPizzaActivity
     │  (clic sur une pizza)
     ▼
PizzaDetailActivity
```

---

## 📂 Fichiers XML importants

| Fichier | Rôle |
|---|---|
| `AndroidManifest.xml` | Déclare les 3 activités, SplashActivity comme LAUNCHER |
| `activity_splash.xml` | FrameLayout avec ImageView centré |
| `activity_list_pizza.xml` | LinearLayout + ListView |
| `row_pizza.xml` | RelativeLayout : image + nom + meta |
| `activity_pizza_detail.xml` | ScrollView avec toutes les infos |
| `res/values/strings.xml` | Nom de l'application |

---

## ⚠️ Erreurs fréquentes et solutions

| Erreur | Cause | Solution |
|---|---|---|
| `cannot find symbol pizza1` | Images absentes de `res/drawable/` | Copier les images dans `res/drawable/` |
| `resource mipmap/pizza1 not found` | Mauvaise référence dans le XML | Remplacer `@mipmap/pizza1` par `@drawable/pizza1` |
| `class, interface or enum expected` | Double déclaration `package` | Supprimer le `package` en double |
| `Cannot resolve symbol R` | Gradle non synchronisé | File → Sync Project with Gradle Files |

---

## 👨‍💻 Auteur

Réalisé dans le cadre du cours de **Développement Mobile Android**  
LAB 6 — Application Recettes de Pizza
