# Les serveurs web avec Go
Un serveur web est un logiciel qui stocke les fichiers qui composent un site web, et les envoi à l'appareil de l'utilisateur (client) qui le visite.
Pour initialiser le serveur, il faut utiliser la fonction `http.ListenAndServe()`. Cette fonction demande comme premier argument une string, représentant le port dédié au serveur et une variable de type Handler. Dans cette situation, cet argument doit valoir `nil`.
```Go
// Déclaration du port.
port := ":8080"
err := http.ListenAndServe(port, nil)
if err != nil {
	log.Fatal(err)
}
```
`log.Fatal()` permet d'imprimer le contenu de l'erreur qui sera transmise (sauf si elle vaut `nil`), et de stopper le programme ensuite.

Une fois`http.ListenAndServe()` executé, le serveur est techniquement lancé, mais il n'a aucune indication sur le comportement qu'il doit avoir, et les opération qu'il doit effectuer. Pour se faire, il faudra appeler `http.HandleFunc()`.

`http.HandleFunc()` attend deux arguments : le chemin URL sous format string, et la fonction à éxécuter.
> Pour plus d'information sur le vocabulaire des URL, consultez "<a href="../url/url.md">url.md</a>".

La fonction à transmettre doit contenir deux arguments précis : une structure `http.ResponseWriter`,  et le pointeur d'une structure `http.Request`.
> Pour des explications sur le rôles des pointeurs, consultez "<a href="../pointers/pointers.md">pointers.md</a>".

```Go
// Exemple pour faire fonctionner la page "localhost:8080/data"
func dataPage(w http.ResponseWriter, req *http.Request) {
	// En insérant le string "Hello World" dans l'objet http.ResponseWriter, 
	// Il sera possible d'écrire directement sur la page internet correspondante.
	fmt.Fprintf(w, "Hello world")
}
func main() {
	http.HandleFunc("/data", dataPage)
	port := ":8080"
	err := http.ListenAndServe(port, nil)
	if err != nil {
		log.Fatal(err)
	}
}
```
> `http.ListenAndServe()` doit <ins>__systématiquement__</ins> se situer en fin de fonction, car rien ne sera lu au-delà de la ligne où la fonction est appelée.