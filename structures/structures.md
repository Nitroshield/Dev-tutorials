
# Les structures

La Structure est un objet permettant de contenir plusieurs variables.

```Go
Exemple :
type  Personne  struct {
	Prenom string
	Age int
}
```

`type` permet de donner un nom à la structure (ici `Personne`) et `struct`, permet à l'ensemble d'être reconnu comme une Structure. Au sein des accolades `{}` il suffit ensuite d'associer un attribut à son type de donnée (ici `Prenom string` & `Age int`). La structure n'a plus qu'à être associée à une variable plus tard dans le code.

```Go
// Exemple de variable basée sur une structure, déclarée vide
var mec Personne

// Exemples d'établissement de valeurs aux attributs de la structure
mec.Prenom = "John"
mec.Age = 30
// <variable>.<attribut> = <valeur>

// OU - Exemple de déclaration de variable basée sur une Structure
mec := Personne{"John", 30}
```

Il est possible de déclarer des tableaux de structures, ex: `[]Personne`, il suffit ensuite de le lires avec les mêmes boucles que celle qui lit les tableaux.

> Il reste conseillé d'utiliser une Majuscule comme première lettre des attributs et des structure afin qu'elles soient traités comme des données globales.
> Pour plus d'information sur les variables globales, constulez "<a href="../variables/variables.md">variables.md</a>".