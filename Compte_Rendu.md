# Jourdan Kevin

AnalyseurLexical.jflex est construit à l'aide de jflex, c'est un générateur de lexer (Analyseur Lexical) pour Java
Il analyse le code source du langage λ-ada en entrée et génère des symboles lexicaux (tokens) utilisés par l'analyseur syntaxique
Il reconnaît les mots-clés, les opérateurs, les identificateurs, les nombres entiers


AnalyseurSyntaxique.cup est généré à l'aide de CUP, un générateur de parseur pour Java.
Il utilise les symboles lexicaux produits par l'analyseur lexical pour construire l'arbre syntaxique abstrait (AST) du code source.
Il définit la grammaire du langage λ-ada et les règles de construction de l'arbre syntaxique abstrait.


Les classes TreeNode et Leaf représentent les nœuds de l'arbre syntaxique abstrait (AST) généré par l'analyseur syntaxique.
La classe TreeNode représente les nœuds internes de l'AST avec un opérateur et éventuellement des enfants.
La classe Leaf représente les feuilles de l'AST, telles que les valeurs littérales (entiers, booléens) ou les identificateurs (comme les noms de variables: prixHt).


Main.java est la classe principale, elle sert de point d'entrée de l'application.
Elle instancie l'analyseur lexical et syntaxique, analyse le code source en entrée et génère le code assembleur correspondant.
Le code assembleur généré est écrit dans un fichier avec l'extension .asm.


Les fichiers ASM (exercice1.asm, exercice2.asm) contiennent le code assembleur généré à partir des codes source λ-ada (exercice1.txt, exercice2.txt) présent dans le dossier 'testfiles'.
Le code assembleur utilise une syntaxe compréhensible par une machine à registres simplifiée.
Il effectue les opérations nécessaires pour exécuter le programme λ-ada sur une machine virtuelle ou un émulateur.
---
# Exercice 1 :
```shell
java -cp .\build\libs\I805_TP2_Lambada.jar fr.usmb.m1isc.compilation.tp.Main .\testfiles\exercice1.txt
```
```shell
java -jar vm-0.9.jar exercice1.asm --debug
```
---
# Exercice 2 :
```shell
java -cp .\build\libs\I805_TP2_Lambada.jar fr.usmb.m1isc.compilation.tp.Main .\testfiles\exercice2.txt
```
```shell
java -jar vm-0.9.jar exercice2.asm --debug
```
