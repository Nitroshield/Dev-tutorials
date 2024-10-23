# Les tableaux
Un tableau est un ensemble de données rassemblées dans une seule variable. En Go l'ensemble des données doivent partager un même type.

En Go un tableau doit être déclaré de la façon suivante (pour cet exemple, un tableau de nombres) :
```Go
// Déclaration standard
var tableau []int = []int{76, 27, 30}
// Déclaration simplifiée
var tableau := []int{76,27,30}
```
Un tableau peut être parcouru par des boucle, donnant l'accès à chacune de ses valeurs individuellement.
> Voir la fiche "<a href="../boucles/boucles.md">boucles.md</a>".

Lorsque l'on explore un tableau via une boucle, l'on peut obtenir les valeurs de chaque ligne grace à leur indexation. Ex: `tableau[index]`, tant que l'index indiqué entre les crochets `[]` est contenue dans le tableau, le contenu de la ligne corespondante sera récupéré, et pourra être modifiable.
Pour reprendre le tableau donné en exemple, `tableau[1]` contient la valeur `27`.
Chaque ligne peut être modifiée si nécessaire, de la même manière que l'on attribuerait une valeur à une variable, simplement en utilisant la variable du tableau en question adjoint à l'index de la ligne ciblée. Ex: `tableau[2] = 0`, fera que la valeur située à l'index 2 de la variable `tableau` sera égale à 0.
> L'indexation commence toujours à partir de 0.

## En golang
En golang, un tableau ou "slice" possède trois propriétées :
- Les valeurs enregistrées
- Le nombre de ligne enregistrés | Pouvant être récupéré avec `len(tableau)`
- Sa capacité maximale

Un tableau peut donc être déclaré avec une capacité maximale définie, ex: `tableau := [3]int{}` contiendra trois entrées maximales et aura une longueur de 3 par défaut. 
>Un tableau ne peut pas avoir plus de lignes en son sein que ce qui lui est défini comme maximum, autrement il résultera une erreur "Out of bounds".

### Ajouts de lignes
Le nombre d'entrées dans un tableau n'est pas figé, des lignes peuvent être ajoutées ou supprimée.
L'ajout se fait avec la fonction `append()`. Précisément, cette fonction attends comme premier argument, un tableau, puis, autant d'arguments, que l'on souhaite ajouter de ligne. Cette fonction retourne le nouveau tableau qui doit donc être placé dans une variable.
> Pour en savoir plus, consulter le document sur les fonctions (wip).

### String : Tableau de bytes
Le type de variable peut aussi être considéré comme un tableau de Bytes.
```Go
Exemple:
var str string = "Golang"
fmt.Println(str[1]) // afficherea 'o'
```
> Les valeurs du tableau cité dans cet exemple ne sont pass modifiables.