# Les conditions
Les conditions permettent dans un code, d'effectuer une ou plusieurs actions selon des cas de figures définis à l'avance. Cette dernière s'articule autour d'un `if` et d'un `else`.
```Go
Exemple:
var counter int = 3
// si (paramètres de la condition) {
if counter > 5 { // Si la condition est remplie, que counter est supérieur à 5
	// code à éxécuter
} else { // Si la condition n'est pas remplie
	// code à éxécuter
}
```
Les conditions peuvent contenir des vérifications secondaires: des `else if`, permettant d'éxécuter un autre code si la première condition n'a pas été remplie. Si aucun `else if` n'a été validé, c'est le code inscrit dans le `else` qui est éxécuté.
Vous n'avez pas besoin de déclarer une `else` si vous déclarez un `if`, l'inverse cependant est impératif.
>Note : Si un `else if` est validé, les `else if` suivant ne seront pas examinés.

## Les opérateurs
Les opérateurs sont les caractères indispensables pour comparer deux valeurs au sein d'une condition.
| Opérateur | Signification |
|----|----|
|== | est égal à |
| < | est inférieur à |
| > | est supérieur à |
| <= | est inférieur ou égal à |
| >= | est supérieur où égal à |
| != | est différent de |

Vous pouvez également vérifier plusieurs cas dans une même condition.
| Symbole | Signification |
|---|----|
|&& | condition A et condition B (valide si toutes les conditions sont remplies)|
| \|\|| condition A ou condition B (valide si au moins une condition est remplie) |
| !| condition A n'est pas valide (souvent utilisé avec les booléens) |

Les conditions testées simultanément ne sont pas limitées qu'à deux. De plus, ces différents symboles peuvent se cotoyer.
## Le cas "switch"
Parfois, vous pourriez avoir besoin d'éxécuter du code selon la valeur d'une seule variable, vous demandant de prendre en compte plusieurs cas de figures, dans cette situation, le switch est une bonne alternative à une cascade de `else if`.
```Go
Exemple :
switch counter {
	// correspond à la condition "if counter == 1 {"
	case 1: /* entrez du code*/
	case 2: /* entrez du code*/
	case 3: /* entrez du code*/
	// Dans le cas où vous auriez besoin d'actions plus complexes :
	case 4: {
		//entrez plusieurs lignes de code à éxécuter
	}
	default: /* entrez du code à exécuter par défaut */
}
```
> Default est l'équivalent du `else` des conditions classiques.