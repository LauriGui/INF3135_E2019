# Séance 3: Arguments, Chaînes de caractères et pointeurs

**Note** : (_facultatif_) S'il y a des questions dans ce labo, répondez y dans un fichier nommé `./labo/reponse-labo.md`.  Le fichier doit être dans un format `Markdown`. Utilisez le projet `inf3135-e2019` pour déposer le fichier `./labo/reponse-labo.md` soit le même que pour vos exercices.  Utilisez un autre `projet` pour vos travaux pratiques.  

##### Format du fichier Markdown
 + Séance 2 (Header 1)
 + Exercice {1..n} (H2)
 + Question {1..n} (H4)
 + S`2`.E`3`.Q`1`  `l'entier` est une valeur qui change bien sûr
 + La réponse dans une section script (code block)

**Note**: Il est recommandé de versionner vos réponses aux exercices à l'aide
de Git. Un seul dépôt est amplement suffisant pour tous les laboratoires, en
divisant les fichiers dans des répertoires.

## 1 - Arguments de la fonction main

Écrivez un petit programme C nomme `cmdline.c` qui accepte un nombre limité et
spécifique en provenance de la ligne de commande.

Vous devez pour faire le traitement des arguments écrire une fonction `int cmdline()`
qui accepte `-c CODE` obligatoire, et les suivants facultatifs `-1 int`,  `-2 int`, 
`-d INC | DEC`. `-d` `-1` et `-2` devront être validé et si une erreur est détectée, 
l'application doit arrêter avec code de retour.

#### code de retour
+ `0` : exécution avec succès;
+ `1` : si -c et/ou le code ne sont pas présents;
+ `2` : si le `-1` et `-2` ne sont pas de type entier naturel N*;
+ `3` : si `-d` et/ou `DEC | INC` ne sont pas présent; 

#### Questions
+ Q1. Quelle instruction vous permet de retourner le code 0?
+ Q2. Quelle instruction vous permet de retourner le code 1?

## 2 - Chaînes de caractères

Écrivez un petit programme C appelé `renverse.c` qui prend tous les arguments
passés en paramètres, les concatène en ordre inverse et affiche le résultat.

On s'attend donc au comportement suivant :

```sh
./renverse alpha beta gamma delta
deltagammabetaalpha

./renverse esope reste et se repose
reposeseetresteesope
```

N'hésitez pas à utiliser la bibliothèque `string.h`.

## 3 - Palindromes

Écrivez une fonction C dont la signature est
```c
bool estPalindrome(const char *s);
```
qui retourne `true` si et seulement si `s` est un palindrome, c'est-à-dire un
mot qui se lit de la même façon de gauche à droite. On s'attend donc à ce que
```c
estPalindrome("radar")
estPalindrome("ici")
estPalindrome("laval")
estPalindrome("!RessasseR!")
estPalindrome("")
estPalindrome("U")
```
retournent `true`, mais que
```c
estPalindrome("Lui")
estPalindrome("Ici")
estPalindrome("laval.")
estPalindrome("Esope reste et se repose.")
```
retournent `false`.

Ensuite, écrivez une fonction C dont la signature est
```c
bool estPhrasePalindrome(const char *s);
```
qui vérifie si une phrase est palindromique, en ignorant la casse
(majuscules/minuscules) et les signes de ponctuation. Ainsi, on s'attend à ce
que
```c
estPhrasePalindrome("Esope reste et se repose.")
estPalindrome("Ici")
```
retournent `true`.

Dans les deux cas, fournissez des tests pour montrer que vos fonctions sont
correctement implémentées.

## 4 - Fouille dans un tableau

Écrivez une fonction C dont la signature est
```c
const double *trouverElement(const double tableau[],
                       unsigned int taille,
                       double element);
```
qui retourne un pointeur vers la première occurrence de `element` dans
`tableau` si elle existe, ou qui retourne `NULL` sinon, sachant que les indices
valides de `tableau` sont entre `0` et `taille - 1`.

---

##### Auteur Guy Francoeur
###### basé sur les travaux d'Alexandre Blondin Massé, Professeur
