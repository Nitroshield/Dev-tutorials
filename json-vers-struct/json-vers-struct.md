# Json vers Structures
Il est possible de transposer des objets Json vers des structures Golang pour du traitement de donnée.
Pour se faire, il faut que la Structure Golang respecte la structure de l'objet Json.

Exemple:

Json :
```Json
{
	Prenom: "John",
	Nom: "Doe",
	Age: 30,
	Adresse : "18 Rue du Labrador"
}
```
Golang :
```Go
type Personne struct {
	Prenom string `json:"Prenom"`
	Nom string `json:"Nom"`
	Age int `json:"Age"`
	Adresse string `json:"Adresse"`
}
```

> Il est important de noter le \`json:"attribut"\` sur la ligne de chaque attribut de la Structure, ce sont ces mentions qui permettront à la fonction de transfert de trouver les correspondances.

La fonction indispensable pour effectuer ce transfert est la fonction `json.Unmarshal()`, elle demande en premier argument, le Json sous format []byte, et en second l'opérateur `&variable` de la variable dans laquelle la structure est déclarée.
> Pour en savoir plus, consultez la fiche "<a href="../pointers/pointers.md">pointers.md</a>".
```Go
Exemple :
// Considérons que le fichier .json est déjà contenu dans la variable jsonContent au format []byte
var perso Personne
json.Unmarshal(jsonContent, &perso) 
fmt.Println(perso.Prenom) // Affichera "John"
```
Si le Json possède des attributs contenant des objets, il faut adapter la Structure avec d'autres Structures.

Json :
```Json
{
	Prenom: "John",
	Nom: "Doe",
	Age: 30,
	Adresse: {
		Numero: "18",
		Rue: "Rue du Labrador",
		Ville: "Moulinsart"
	}
}
```
Golang :
```Go
type Personne struct {
	Prenom string `json:"Prenom"`
	Nom string `json:"Nom"`
	Age int `json:"Age"`
	Adresse PersoAdresse `json:"Adresse"`
}
type PersoAdresse struct {
	Numero string `json:"Numero"`
	Rue string `json:"Rue"`
	Ville string `json:"Ville"`
}
```
> Pour en savoir plus sur la structure des objets Json, consultez le document "<a href="../json/json.md">json.md</a>".