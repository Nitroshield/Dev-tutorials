# Les Fonctions
Les fonctions sont des opérations incontournables du développement. Elles permettent d'éxécuter, à l'endroit où elles sont appelées des opérations redondantes sans avoir à incorporer ou répéter la même portion de code.
Une fonction se reconnait à sa syntaxe : 
```Go
func myFunction(data string) {
```
Dans cet exemple, la fonction `myFunction` est prête à être appelée, attendant à ce qu'une variable de type `string` lui soit transmise en tant qu'argument. Le nombre d'argument dans une fonction n'est pas limité.
Dans cette fonction, la donnée qui sera transmise à la fonction sera stockée sur la variable `data`.

En Go, si des valeurs de retour sont attendue, son type doit être défini lors de la déclaration de la fonction, si plusieurs données sont renvoyées, ces types sont encadrées de parenthèses `()`, séparées d'une virgule `,`. 
```Go
Exemple :
// Déclaration de fonction avec une donnée de retour
func myFunction(argument string) string {
// Déclaration de fonction avec plusieurs données de retour
func myFunction(argument string) (string, string) {
```
Les variables déclarées dans les parenthèses des fonctions sont des variables locales.

#### Cas pratique
```Go
// Si l'on appelle la fonction double(), elle serait déclarée ainsi :
// La fonction double récupère une donnée de type int, et doit retourner une donnée int.
// La seconde doit être le double de la première.
func double(number int) int {
	// return est l'instruction qui permet de renvoyer une donnée,
	// ici number multiplié par deux.
	return number*2
}

var nb int = double(5)
fmt.Println(nb) // Affichera 10
```