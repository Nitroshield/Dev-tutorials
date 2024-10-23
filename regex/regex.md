# Les expressions régulières
Les expressions régulières sont une méthode de sélection et de remplacement présente dans quasiment tous les langages de programmation. Bien que ces expressions soient difficiles à lire pour des néophytes, ces dernières sont extrêmement précises et efficaces.
> Pour expérimenter les "regEx", rendez-vous sur le site <a target=_blank href="https://www.regex101.com">regex101</a>.

## Les sélecteurs
Au-delà de la recherche par caractère, il existe des moyens d'effectuer des sélections plus larges, en voici quelques exemples :

| Sélécteur | Effet |
|----|-----|
|[abc] | Caractères compris entre les crochets |
|[a-c] | Caractères entre a & c (donc a,b,c) |
| [^abc] | Caractères excluant la séléction, que ce soit une séléction [abc], même fonctionnement pour [^a-c] |
| x\|y | Un caractère (ou sélection) ou une autre.
| {unNombre}| Se place après une séléction ou un caractère; la séléction doit être répétée ce nombre précis de fois. |
| {1, 4}| Se place après une séléction ou un caractère; la sélection doit être répétée entre 1 et 4 fois. Il peut y avoir un nombre sur les deux, ce qui n'imposera qu'un minimum ou maximum selon le nombre conservé.|
|?| Se place après une séléction ou un caractère; rend le caractère ou la séléction facultative.|
| . | Sélectionne n'importe quel caractère. |
|(abc) | Isole une sélection ou plusieurs caractères (surtout utilisé pour les remplaçements). |
|^abc | Se place au début de l'expression; impose que la sélection soit placée au début |
|abs$ | Se place à la fin de l'expression; impose que la sélection soit placée à la fin |
|+| Se place après un caractère ou une séléction; la séléction doit être présente une ou plusieurs fois. |
|*| Se place après un caractère ou une séléction; la sélection doit être présente une fois, plusieurs fois, ou pas du tout.
| \\ | Permet d'échapper un caractère pour l'utiliser comme tel. |
|\w | Sélection d'un caractère alphanumérique, correspond à [a-zA-Z0-9] |
|\s | Sélection d'un caractère vide (espace, tabulation, saut de ligne)|
|\n | Séléction d'un saut de ligne |
|\d | Séléction d'un caractère numérique, correspond à [0-9]|
|\D, \W, \S|Ces sélécteurs peuvent être utilisés pour sélectionner l'inverse de la sélection minuscule. (ce qui n'est pas numérique; ce qui n'est pas alphanumérique; ce qui n'est pas un caractère vide)|

```
Exemples :
// Si on cherche une regex pour identifier une extension comme celle d'une image (png, jpg, bmp, gif) :
"image.png" | regex: /.+\.(png|jpg|bmp|gif)$/i
	/  : le slash / démarre la séléction de l'expression régulière.
	.+ : le caractère point . séléctionne n'importe quel caractère, le + indique qu'on en attend un ou plus.
	\. : on échappe le caractère du point, début de l'extension.
	(  : on ouvre la parenthèse pour déclarer un groupe de séléctions
	png|jpg|bmp|gif : on regroupe les ensembles de caractères "png", "jpg", "bmp" et "gif" séparés d'une barre verticale | pour indiquer que ça peut être l'un de ces ensembles.
	)  : on referme le groupe de séléctions
	$  : impose que la sélection soit à la fin de la string analysée (nous cherchons à reconnaitre une extension après tout.)
	/i : le i après l'expression implique que cette dernière ne fera pas de distinctions entre minuscules et majuscules
```
> En go, les `/` encadrant la regex ne sont pas à mettre.

## Les options de l'expression
Les expressions peuvent avoir une ou plusieurs options modifiant le comportement ou la portée de cette dernière sur la string qu'elle analyse. A chaque lettre correspond une option pouvant se cumuler.
|Option| Comportement |
|----|----|
|g | L'expression n'arrête pas sa lecture après la première occurence.|
|m| Fait en sorte que ^ & $ représentent les début et fin de chaque ligne.|
|i| Ne prend pas en compte l'aspect majuscule ou minuscule des caractères |
|s| N'interpête pas les sauts de lignes, faisant en sorte que la séléction ne soit qu'une seule ligne.|

> Il existe d'autres sélections et d'autres options explorables dans regex101.

Une expression régulière est souvent encadrée par des slashs `/`, l'option de l'expression se place après le slash fermant.