## Objectif du projet

L’objectif est de choisir des grandeurs d’intérêt, par exemple :

- la **probabilité de réussite d’un tir** selon la distance,  
- l’**impact du temps restant** ou du **nombre de dribbles** sur la réussite,  
- ou encore la **différence de performance à domicile et à l’extérieur**.

---

## Partie théorique — Estimateurs et propriétés statistiques

### 1. Choix des grandeurs d’intérêt

Dans ce projet, on s’intéresse principalement à la **probabilité de réussite d’un tir** en fonction de plusieurs variables explicatives (distance, temps, contexte du match).

La grandeur d’intérêt principale est donc la **proportion de tirs réussis**, notée :

\[
p = \mathbb{P}(\text{tir réussi})
\]

Chaque observation du jeu de données contient une variable binaire :

\[
X_i =
\begin{cases}
1 & \text{si le tir est réussi (SHOT\_RESULT = "made shot")} \\
0 & \text{sinon (SHOT\_RESULT = "missed shot")}
\end{cases}
\]

---

### 2. Estimateur de la proportion de réussite

L’estimateur naturel de \( p \) est la **moyenne empirique** :

\[
\hat{p} = \frac{1}{n} \sum_{i=1}^{n} X_i
\]

#### 🔹 Propriétés

- **Espérance :**  
  \[
  \mathbb{E}[\hat{p}] = p
  \]
  L’estimateur est **sans biais**.

- **Variance :**  
  \[
  \mathrm{Var}(\hat{p}) = \frac{p(1 - p)}{n}
  \]

- **Erreur standard :**  
  \[
  \mathrm{SE}(\hat{p}) = \sqrt{\frac{\hat{p}(1 - \hat{p})}{n}}
  \]

---

#### 🔹 Intervalle de confiance (IC à 95%)

Sous l’hypothèse d’un grand échantillon (\(n > 30\)), on a :

\[
\hat{p} \sim \mathcal{N}\left(p, \frac{p(1-p)}{n}\right)
\]

Ainsi, un **intervalle de confiance à 95 %** est donné par :

\[
IC_{95\%} = \left[\hat{p} - 1.96 \times SE(\hat{p}), \; \hat{p} + 1.96 \times SE(\hat{p})\right]
\]

Cet estimateur permet de comparer, par exemple :
- la proportion de tirs réussis à domicile et à l’extérieur,  
- ou la proportion selon des classes de distance de tir.

---

### 3. Extension : distance moyenne des tirs réussis

On peut également étudier la **distance moyenne des tirs réussis**, notée \(\mu\), avec l’estimateur :

\[
\hat{\mu} = \frac{1}{m} \sum_{i=1}^{m} Y_i
\]

où \(Y_i\) représente la distance (en pieds) d’un tir réussi.

#### 🔹 Propriétés

- **Sans biais :**  
  \[
  \mathbb{E}[\hat{\mu}] = \mu
  \]
- **Variance :**  
  \[
  \mathrm{Var}(\hat{\mu}) = \frac{\sigma^2}{m}
  \]
- **Erreur standard :**  
  \[
  \mathrm{SE}(\hat{\mu}) = \frac{s}{\sqrt{m}}
  \]

---

### 4. Validation empirique

Pour valider ces estimateurs sur les données NBA :
- on calcule \(\hat{p}\) et \(\hat{\mu}\) sur l’échantillon observé,  
- on estime leurs erreurs standards et intervalles de confiance,  
- et on **visualise** les résultats via :
  - des **diagrammes en barres** (comparaison domicile/extérieur),  
  - des **distributions** (distances des tirs réussis),  
  - ou des **nuages de points** (impact du nombre de dribbles sur la réussite).

Ces analyses permettent de mieux comprendre les **facteurs influençant la performance des joueurs**.

---
