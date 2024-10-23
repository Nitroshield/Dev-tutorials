# L'Objet Json (JavaScript Object Notation)
Json est une méthode incontournable pour stocker et transmettre de grandes quantité de données variées, que ce soit entre deux programmes, ou en interne d'une même application. Cet objet est supporté par de nombreux langages et est parfaitement compatible avec **Golang** ou **Javascript**.

Comme tout Objet, la lecture de Json commence par un couple d'accolades `{}` dans lequel sera inscrit son contenu.
L'ensemble du format Json fonctionne par couple `Attribut : valeur`, il peut s'agir d'une donnée, ou d'un autre objet.
```Json
Exemple :
{
	Personne : {
		Prenom: "John",
		Nom: "Doe",
		Age: 30
	}
}
```
Chaque attribut est séparé du suivant par une virgule.
Dans le cas d'un tableau, son contenu doit être inscrit entre crochets `[]`.
```Json
Exemple :
{
	Coordonnees : [13, 0, 127]
}
```
Les informations de l'objet Json peuvent être stockées dans des fichiers `.json`.