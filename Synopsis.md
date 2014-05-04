Le lien improbable entre la Programmation Fonctionnelle et l'Entreprenariat
===========================================================================
Qui: Xavier Tordoir et Andy Petrella
Lieu: Université de Liège, cours de Programmation Fonctionnelle donné par Pr. Gribomont à l'institut de Montéfiore.
Date: Le 8 mai 2014

Intro
-----
* Xavier
* Andy

Temps: 5'

Studying =:= Future[Option[Job]]
--------------------------------

Temps: 2'

Job =:= (Work => Option[Experience]) => Option[Money]
-----------------------------------------------------
Temps: 3'

Job =:= ((Work, Explore, Learn) => Option[Expertize]) => Option[(Money, Future[Job])]
-------------------------------------------------------------------------------------
Temps: 5'


FTW[FP]
-------
Les raisons de choisir la FP aujourd'hui,
* le web (REST, ...): Future et immutabilité
* architecture explosée en services: composabilité naturelle des fonctions. micro-service ~ fonction
* le distributed computing: immutabilité et message passing style
* le big data: lambda architecture

Temps: 10'

Future[Conquier[Future[Divide]]]
--------------------------------
* Lazy eval et async en FP.
* Distributed computing et data analysis 

Temps: 10'

~~Await~~[_]
------------
* Faire un wrap up sur les questions des études, de l'apprentissage et de la recherche.
* Rappeler pourquoi que la FP est un pari sur un futur proche, voir déjà actuel.
* Appuyer une fois encore sur l'importance du lazy, async et du data computing en général.
* Parler des pays émérgents, donc des réaison de ne pas attendre et ne pas se reposer.

Temps: 10' (5' pour le dernier point)

Eval[Expression]
----------------
Proposer quelques exemples d'outils en Scala.

## Scala
* FP
* OO
* Case class

Temps: 10'

## Play! Framework 2
* Expliquer rapidement les concepts derrière Play, le CPS et l'immutabilité.
* Pas de session, immutabilité et event-loop.
* Un projet d'explication.

Temps: 15'

## Akka
* Message passing style
* Immutabilité des messages
* Mutabilité des actors et Thread-Confinement
* Un petit exemple explicatif

Temps: 15'

## Spark
* concept d'RDD
* concept d'un DAG
* concept du lineage pour l'aspect resilient.

Temps: 10'

___

Calcul du temps théorique:

```scala
val synopsis = io.Source.fromFile(new java.io.File("./Synopsis.md"))
synopsis.getLines
        .filter(_.startsWith("Temps:"))
        .map(_.drop("Temps:".size)
              .dropWhile(_ == ' ')
              .takeWhile(_ != '\'')
              .mkString
              .toInt
            )
        .sum
```





