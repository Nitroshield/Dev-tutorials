# Les Boucles
Les boucles sont une instruction permettant de répéter la portion de code qu'elle encadre. En Golang elle peut se déclarer de deux façon distinctes :
```Go
// boucle numérique, avec une variable servant au contrôle de l'opération
for i:= 0; i < 5; i++ {
	fmt.Println(i) // Imprimera 0, puis 1, 2, 3 et 4.
}
// boucle de lecture, utilisant un tableau dans une variable, et s'arrêtant une fois la dernière ligne lue
for index, element := range tableau {
	// code à répéter
}
```
Dans le premier cas, la boucle est initialisée par trois status séparés par un point-virgule `;` :
- La variable servant au contrôle de la boucle
- La condition qui doit être valide pour que la boucle soit engagée et répétée
- L'opération appliquée à la variable de contrôle.

Dans cet exemple, la variable `i` est définie à zéro, et augmentera de `1` à chaque fin de la boucle, l'opération ++ équivaut à ajouter 1 à la variable, l'opération -- permet l'opération inverse.
A chaque début de boucle, la codition `i < 5` sera évaluée, si elle est valide, la boucle se relancera, autrement, la boucle sera considérée comme terminée, et la suite du code sera lu.

Dans le second cas, l'opération `for range` permet de prendre `tableau`, et de parcourir le contenu de ce dernier. La première variable déclarée est la position de la ligne dans le tableau (ici `index`), et le second, le contenu de la ligne correspondante . Une fois la dernière ligne lue, la boucle s'arrête, considérée comme terminée.
>**Attention** : Vous ne pouvez pas modifier le contenu de `tableau` en modifiant la valeur de `element` !
> Notes : Les variables déclarée pour les boucles sont des variables locales.