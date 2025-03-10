# Séance 6: Type abstrait de données et modularité

**Note** : (_facultatif_) S'il y a des questions dans ce labo, répondez y dans un fichier nommé `./labo/reponse-labo.md`. Le 
fichier doit être dans un format `Markdown`. Utilisez le projet `inf3135-e2019` pour déposer le fichier `./labo/reponse-labo.md`
soit le même que pour vos exercices. Utilisez un autre `projet` pour vos travaux pratiques.

##### Format du fichier Markdown
 + Séance 2 (Header 1)
 + Exercice {1..n} (H2)
 + Question {1..n} (H4)
 + S`2`.E`3`.Q`1` (strong) `est une valeur qui change bien sûr`
 + La réponse dans une section script (code block)

**Note**: Il est recommandé de versionner vos réponses aux exercices à l'aide
de Git. Un seul dépôt est amplement suffisant pour tous les laboratoires, en
divisant les fichiers dans des répertoires.

## 1 - Implémentation d'une pile (*stack*)

- Une pile contient des objets insérés et retirés selon le principe dernier inséré, premier sorti (last-in-first-out LIFO);
- Les objets peuvent être insérés à tout moment, mais seulement le dernier (le plus récemment inséré) peut être retiré;
- La _stack_ est ordonné;

```c
// stack.h

//libre à vous, faites votre implémentation
//je vais vérifier les solutions
```

+ Q1. Quel est la différence entre les mots anglais suivant : stack vs pile vs heap ?
+ Q2. Produire un fichier entête (.h).
+ Q3. Produire un fichier source (.c).
+ Q4. Produire un fichier test_stack.c qui est dépendant des deux premiers.
+ Q5. Produire un fichier Makefile pour automatiser certaines tâches.

## 2 - Implémentation d'une file (*queue*)

Complétez l'implémentation d'une structure de données de type "file" (en anglais *queue*) à partir des déclarations suivantes:

```c
typedef struct Queue_s {
  int capacity;
  int size;
  int front;
  int rear;
  int *elements;
} Queue_t;

extern Queue_t * initQ(int maxQueueSize);
extern void dequeueQ(Queue_t *Q);
extern int frontQ(Queue_t *Q);
extern void enqueueQ(Queue_t *Q,int element);
extern void deleteQ(Queue_t *Q); // finir par ceci (bien vu Fanny)
```

+ Dans cet exercice, nous voulons prendre de bonne habitude, et tenter de réaliser un `type abstrait de données` de façon autonome.
+ Le but est de le rendre le `type abstrait` le plus complet possible sans optimiser.
+ Il n'y a pas de mauvaise réponse à priori.
+ Assurez-vous de gérer correctement la mémoire (sans fuite de mémoire)!

Questions:
+ Q1.  Quelle est la difficulté que vous avez rencontrée ?
+ Q2.  Avez-vous des fuites de mémoire ou des accès illicites à des zones mémoires (*out of bounds*) ?

## 3 - Implémenter un Array Dynamique (*Vector*)

Dans cet exercice vous devez construire une structure de données capable d'accepter un nombre `limite de int` d'éléments.
Lors de la création, vous devez déterminer la capacité, exemple 2.  Lorsque cette capacité sera insuffisante, vous devrez
étendre le Vecteur.

Voici la définition et les prototypes

```c
typedef struct {
  int size;      // slots used so far
  int capacity;  // total available slots
  int *data;     // array of integers we're storing
} Vector_t;

extern void initV(Vector_t *vector, int capacity);
extern void appendV(Vector_t *vector, int value);
extern int getV(Vector_t *vector, int index);
extern void setV(Vector_t *vector, int index, int value);
static void extendV(Vector_t *vector);
extern void freeV(Vector_t *vector);
```

Questions :
+ Q1. Quelle est la difficulté que vous avez rencontrée ?
+ Q2. Avez-vous des fuites de mémoire ou des accès illicites à des zones mémoires (*out of bounds*) ?
+ Q3. Avez-vous eu recours a internet ou des exemples pour compléter l'exercice ?

## 4. Bonus 
