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
Rappeler aux étudiants qui semblent l'avoir oublié (comme nous même l'avions oublié à notre époque) que les études servent principalement à avoir un job plus tard. Et si possible, un job intéressant.

Que donc, il serait judicieux de penser dès maintenant quels seraient les domaines dans lesquels ils aimeraient évoluer et donc doivent acquérir les bases.

Temps: 2'

Job =:= (Work => Option[Experience]) => Option[Money]
-----------------------------------------------------
Comment est traditionnellement vu un Job...

Temps: 3'

Job =:= ((Work, Explore, Learn) => Option[Expertize]) => Option[(Money, () => Future[Option[Job]])]
-------------------------------------------------------------------------------------
Comment un Job devrait être perçu aussi bien par les employés, employeurs, indépendants.

Note: Le `() => Future[Option[Job]` exprime la possibilité de changer des job (sans le garantir), et donc lorsqu'on en a déjà un (`Money`).


Temps: 5'


FTW[FP]
-------
Les raisons de choisir la FP aujourd'hui,
* le web (REST, ...): Future et immutabilité
* architecture explosée en services: composabilité naturelle des fonctions. micro-service ~ fonction
* le distributed computing: immutabilité et message passing style
* le big data: lambda architecture

Temps: 10'

Future[Conquer[Future[Divide]]]
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
* concept d'RDD: read-only, partitioned collection of records
* concept d'un DAG
* concept du lineage pour l'aspect resilient.

Temps: 10'

## More data to Process...
##### Industrial data
* energy
* production lines
* finance
* transport
* ...

##### Personal data
* Internet Era1: few control the content
* Internet Era2: Lots of end-users feed manually (posts, photo, video...)
=> Lots of data, not everything is exploited yet
* Internet Era3: Lots of captors per end user
=> Lots^Lots of data

###### Why?
* There is always a time when we regret that we didn't keep that data...
* Something of value is encoded in data we collect
* We human need a collaborative "consciousness" to evolve as a society 

## All on the mobile, really?
* Data can be available from anywhere
* But in small quantity, network is the bottleneck
* We keep raw data because more might be extrated in the future
* Providing content = aggregating distributed data to produce ... smalldata

## IT is a commodity
* Infrastructure (IaaS): cloud storage, cloud servers...
* Software (SaaS): user management, social login, product support, online payment, access to data sources
* Everything done is distributed
* ...even development

## The tech startup
* Gathers distributed datasources
* Calls distributed services
* Collects raw data
* Does some aggregation
* Scales resources and costs
* Managing distributed resources is a key!

## FP?
The reason FP might get a global adoption is the distributed environment we face.
A very complex distribution over threads, cores, servers, datacenters.
FP describes the result you want, not how you get it
FP deals with Asynchronous calls (who's waiting?)
What about failure?

## Can we do FP in industry?
Popular languages with fp and oo
* javascript ... no types, on a single thread
* ruby with duck typing, no multi-threading
* Java 8?
* scala

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





