
# Les Variables

Les variables sont une composante essentielle du code, quel que soit le langage utilisé. Elle permettent de stocker et traiter des données ponctuelles, saisies, issues d'algorithmes ou de bases de données, etc.

## Golang

En **Golang**, on peut déclarer une variable selon quelques patternes spécifiques :

```Golang
// nomDeLaVariable TypeDeVariable = ValeurDeLaVariable
var  myStr  string = "MyString" // Déclaration classique

myStr := "MyString" // Déclaration simplifiée

var myStr string // Déclaration de variable vide
```

A l'exception de la déclaration simplifiée, en golang le type de variable attendue doit très souvent, si ce n'est toujours être spécifiée.

| Type | Déclaration | Syntaxe |
|--------|--------------|-----------|
| Texte | String | "MyString" |
| Nombre Entier | Int | 0 |
| Nombre à virgule | Float32 ou Float64 | 0.0 |
| Condition (vrai/faux) | Bool | true ou false |

Des variables peuvent être déclarées vide, si, lors de sa déclaration, aucune valeur ne lui est assignée (impossible en déclaration simplifiée). 
Dans le cas des Bool (Booléens) ils sont faux par défaut.
  

## Manipulation des variables

Les variables peuvent être traitées, transformées etc. selon le besoin et leur type.

Les valeurs numériques peuvent se voir ajoutées une valeur, tant que cette dernière est au bon format.

```
Exemples (nombres):
var counter int = 2
counter = counter + 3 // counter vaut désormais 5

var counter float64 = 2.0
counter += 3.0 // counter vaut désormais 5.0

var counter int = 3
counter *= 3 // counter vaut désormais 9

```

Dans le cadre des variables texte, la concaténation permet de fusionner deux variables string en une seule.

```
Exemples (textes):
var str string = "firstString"
str = str + "secondString" 

str += "secondString"
// str vaudra "firstStringsecondString" dans les deux cas
```
  
## Globalité et Localité des variables

Une variable peut être globale ou locale, lorsqu'elle est globale, elle peut être utilisée sur l'ensemble du programme, mais elle doit être déclarée en dehors de toute fonction. Autrement, elle sera locale, et sa portée sera limitée à la fonction en elle-même. Selon le langage, la portée des variables locales peut être plus limitée.
```Golang
Exemples :
var globalVar string // Variable globale effective partout 
func myFunc() {
	var localVar string // Variablelocale effective uniquement dans la fonction
	for (i := 0; i < 5; i++) { // Boucle de répétition
		var localestVar string // Variable locale effective qu'au sein de la boucle
	}
}
```

> Pour des explications plus exhaustives, veuillez vous référer au document "<a href="variables.md">variables.md</a>"