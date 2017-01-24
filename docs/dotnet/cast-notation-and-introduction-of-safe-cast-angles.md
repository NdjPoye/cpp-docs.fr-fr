---
title: "Notation cast&#233;e et introduction de safe_cast &lt; &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "effectuer un cast"
  - "casts de style C et /clr, motivation pour une nouvelle notation de cast"
  - "safe_cast (mot clé C++)"
ms.assetid: 4eb1d000-3b93-4394-a37b-8b8563f8dc4d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Notation cast&#233;e et introduction de safe_cast &lt; &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La notation castée a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 La modification d'une structure existante est une expérience différente et plus complexe que l'élaboration de la structure initiale.  Les degrés de liberté sont moins nombreux, et la solution tend à un compromis entre une restructuration idéale et la réalité, au vu des dépendances structurelles existantes.  
  
 Il en est de même pour les extensions de langage.  À l'aube des années 1990, au moment où la programmation orientée objet est devenue un véritable paradigme, la nécessité d'une fonctionnalité de cast aval de type sécurisé en C\+\+ s'est révélée pressante.  Un cast aval est une conversion, rendue explicite par l'utilisateur, d'un pointeur ou d'une référence de classe de base vers un pointeur ou une référence d'une classe dérivée.  Le cast aval requiert un cast explicite.  La raison en est que le type réel du pointeur de classe de base est un aspect de l'exécution ; le compilateur ne peut donc pas le vérifier.  Autrement dit, une fonctionnalité de cast aval, tout comme un appel de fonction virtuelle, requiert une certaine forme de résolution dynamique.  Cela soulève deux questions :  
  
-   Pourquoi ne pourrait\-on pas se passer de cast aval dans le modèle orienté objet ?  Le mécanisme de fonction virtuel n'est\-il pas suffisant ?  En d'autres termes, pourquoi ne pas considérer qu'une situation nécessitant un cast aval \(ou un cast quelconque\) est une erreur de conception ?  
  
-   Pourquoi la prise en charge d'un cast aval devrait\-elle poser problème en C\+\+ ?  Après tout, elle n'en pose aucun dans des langages orientés objet tels que Smalltalk ou, après lui, Java et C\# ?  Qu'est\-ce qui peut donc compliquer cette prise en charge dans C\+\+ ?  
  
 Une fonction virtuelle représente un algorithme dépendant du type commun à une famille de types. \(Nous ne parlons pas ici des interfaces qu'ISO\-C\+\+ ne prend pas en charge, mais qui sont disponibles dans la programmation du CLR et représentent une alternative de conception intéressante.\)  La conception de cette famille est en général représentée sous la forme d'une hiérarchie de classes dans laquelle existent une classe de base abstraite, qui déclare l'interface commune \(les fonctions virtuelles\), et un jeu de classes dérivées concrètes, qui représentent la famille de types réelle dans le domaine d'application.  
  
 Par exemple, dans un domaine d'application tel que l'Imagerie générée par ordinateur \(CGI\), une hiérarchie `Light`, aura des attributs communs, tels que `color`, `intensity`, `position`, `on`, `off`, etc.  Il est possible de contrôler différentes sources lumineuses, via l'interface commune, sans avoir à se soucier de ce que telle ou telle lumière est un projecteur, une lumière directionnelle, non directionnelle \(pensez au soleil\), ou même une lumière filtrant à travers une porte de grange.  Dans ce cas, le cast aval en un type de lumière particulier pour mettre en pratique son interface virtuelle est inutile.  Dans un environnement de production, toutefois, la vitesse est essentielle.  On peut choisir d'effectuer un cast aval et d'appeler explicitement chaque méthode si, ce faisant, l'exécution inline des appels peut être exercée à la place du mécanisme virtuel.  
  
 Ainsi, une des raisons d'effectuer un cast aval en C\+\+ est de supprimer le mécanisme virtuel, en échange d'un gain significatif de performances à l'exécution. \(Remarquez que l'automatisation de cette optimisation manuelle est un domaine dans lequel la recherche est très active.  Il est toutefois plus difficile de la résoudre que de remplacer l'utilisation explicite des mots clés `register` ou `inline`\).  
  
 Une autre raison d'utiliser un cast aval tient à la nature double du polymorphisme.  On peut voir le polymorphisme comme divisé en une paire de formes, passive et dynamique.  
  
 Un appel virtuel \(et une fonctionnalité de cast aval\) constitue une utilisation dynamique du polymorphisme : il s'agit d'exécuter une action basée sur le type réel du pointeur de classe de base pour cette instance particulière au cours de l'exécution du programme.  
  
 L'assignation d'un objet de classe dérivée à son pointeur de classe de base, toutefois, est une forme passive de polymorphisme, qui utilise ce dernier comme un mécanisme de transport.  C'est l'utilisation principale d'`Object`, par exemple, en programmation du CLR pré\-générique.  Lorsqu'il est utilisé passivement, le pointeur de classe de base choisi pour le transport et le stockage offre en général une interface trop abstraite.  Par exemple, `Object` fournit en gros cinq méthodes à travers son interface ; tout comportement plus spécifique requiert un cast aval explicite.  Par exemple, si nous souhaitons régler l'angle de notre projecteur ou son taux de diminution, il nous faut effectuer un cast aval explicite.  Une interface virtuelle au sein d'une famille de sous\-types ne peut pas, pour des raisons pratiques, être un sur\-ensemble de toutes les méthodes possibles de ses nombreux enfants. Une fonctionnalité de cast aval sera donc toujours nécessaire dans un langage orienté objet.  
  
 Dans ce cas, pourquoi aura\-t\-il fallu attendre si longtemps pour que C\+\+ se dote d'une telle fonctionnalité ?  Le problème est de pouvoir rendre disponibles au pointeur les informations concernant le type à l'exécution.  Dans le cas d'une fonction virtuelle, les informations d'exécution sont installées en deux parties par le compilateur :  
  
-   La classe objet contient un membre pointeur de table virtuelle supplémentaire \(au début ou à la fin de la classe objet\) ; sujet dont l'historique est intéressant par lui\-même\) qui adresse la table virtuelle appropriée.  Par exemple, un objet projecteur adresse une table virtuelle de projecteur, une lumière directionnelle une table virtuelle de lumière directionnelle, etc.  
  
-   Chaque fonction virtuelle dispose d'un emplacement fixe qui lui est associé dans la table, et l'instance réelle à appeler est représentée par l'adresse stockée dans la table.  Par exemple, le destructeur `Light` virtuel peut être associé à l'emplacement 0, `Color` à l'emplacement 1, et ainsi de suite.  C'est là une stratégie efficace, bien que rigide, parce qu'elle est mise en place au moment de la compilation et représente une charge mémoire minime.  
  
 Le problème, alors, est de rendre les informations de type disponibles au pointeur sans modifier la taille des pointeurs C\+\+, soit, en ajoutant une deuxième adresse, soit en ajoutant une forme quelconque d'encodage de type.  Or, cela ne paraissait pas acceptable par les programmeurs \(ni par les programmes\) qui avaient choisi de ne pas utiliser le modèle orienté objet, lesquels représentaient encore la majorité des utilisateurs.  Une autre possibilité consistait à introduire un pointeur spécial pour les types de classe polymorphes, ce qui entraînait alors une situation pour le moins confuse et rendait très difficile la combinaison des deux systèmes, posant en particulier des problèmes d'opérations arithmétiques sur les pointeurs.  Il n'était pas non plus envisageable de conserver une table à l'exécution qui associe chaque pointeur à son type couramment associé, et de la mettre à jour dynamiquement.  
  
 Il faut comprendre que l'on a par ailleurs affaire à deux communautés d'utilisateurs dont les besoins de programmation sont différents, mais tous légitimes.  La solution doit donc représenter un compromis entre ces deux groupes et offrir non seulement à chacun la satisfaction de ses besoins propres mais aussi la possibilité d'interagir.  Cela signifie que les solutions offertes par l'une et l'autre partie seront probablement irréalisables et que la solution finalement élaborée sera imparfaite.  La résolution du problème tourne en réalité autour de la définition d'une classe polymorphe : une classe polymorphe est une classe qui contient une fonction virtuelle.  Une classe polymorphe prend en charge un cast aval dynamique de type sécurisé.  Cela résout le problème consistant à conserver la correspondance pointeur\/adresse puisque toutes les classes polymorphes contiennent ce membre pointeur supplémentaire vers leur table virtuelle associée.  Les informations de type associées, par conséquent, peuvent être stockées dans une structure de table virtuelle développée.  Le coût du cast aval de type sécurisé ne touche \(presque\) que les utilisateurs de la fonctionnalité.  
  
 Le problème suivant concernant le cast aval de type sécurisé était sa syntaxe.  Puisqu'il s'agit d'un cast, la proposition d'origine faite à la commission ISO\-C\+\+ consistait à utiliser la syntaxe de cast sans ornement, comme dans cet exemple :  
  
```  
spot = ( SpotLight* ) plight;  
```  
  
 mais celle\-ci fut rejetée dans la mesure où elle ne permettait pas à l'utilisateur de maîtriser le coût du cast.  Si le cast aval dynamique de type sécurisé a la même syntaxe que la notation de cast qui était jusqu'ici dangereuse mais statique, il devient alors une substitution, et l'utilisateur n'a aucun moyen de supprimer les charges mémoire à l'exécution dans les cas où il est inutile, voire trop coûteux.  
  
 En général, en C\+\+, il existe toujours un mécanisme grâce auquel supprimer les fonctionnalités prises en charge par le compilateur.  Par exemple, il est possible de désactiver le mécanisme virtuel, soit à l'aide de l'opérateur de portée de classe \(`Box::rotate(angle)`\), soit en appelant la méthode virtuelle via un objet de classe \(plutôt qu'un pointeur ou une référence à cette classe\).  Cette dernière suppression, qui n'est pas requise par le langage, est une question de qualité d'implémentation, semblable à la suppression de la construction d'un élément temporaire dans une déclaration de la forme :  
  
```  
// compilers are free to optimize away the temporary  
X x = X::X( 10 );  
```  
  
 La proposition a donc été revue et plusieurs autres notations envisagées. La nouvelle version soumise à la commission était de la forme \(`?type`\), qui indiquait sa nature indéterminée et donc dynamique.  Mais bien qu'elle offre la possibilité de basculer entre les deux formes, statique ou dynamique, personne n'en était réellement satisfait.  On retourna donc à la planche à dessin.  La troisième tentative de notation, qui fut la bonne, est le standard désormais actuel `dynamic_cast<type>`, généralisé depuis en un jeu de quatre notations de cast du nouveau style.  
  
 En ISO\-C\+\+, `dynamic_cast` retourne `0` lorsqu'on l'applique à un type pointeur inapproprié, et lève une exception `std::bad_cast` si on l'applique à un type référence.  Dans les Extensions managées pour C\+\+, l'application de `dynamic_cast` à un type référence managé \(à cause de sa représentation de pointeur\) a toujours retourné `0`.  `__try_cast<type>` a été présenté comme un analogue à l'exception qui lève la variante du `dynamic_cast`, mais il lève `System::InvalidCastException` si le cast échoue.  
  
```  
public __gc class ItemVerb;  
public __gc class ItemVerbCollection {  
public:  
   ItemVerb *EnsureVerbArray() [] {  
      return __try_cast<ItemVerb *[]>  
         (verbList->ToArray(__typeof(ItemVerb *)));  
   }  
};  
```  
  
 Dans la nouvelle syntaxe, `__try_cast` a été transformé en `safe_cast`.  Voici le même fragment de code dans la nouvelle syntaxe :  
  
```  
public ref class ItemVerb;  
public ref class ItemVerbCollection {  
public:  
   array<ItemVerb^>^ EnsureVerbArray() {  
      return safe_cast<array<ItemVerb^>^>  
         ( verbList->ToArray( ItemVerb::typeid ));  
   }  
};  
```  
  
 Dans le monde managé, il est important que le code reste vérifiable. Cela passe par la limitation de la liberté des programmeurs à effectuer des casts entre types avec du code non vérifiable.  Il s'agit là d'un aspect essentiel du paradigme de programmation dynamique que représente la nouvelle syntaxe.  Pour cette raison, les instances de casts dans l'ancien style sont transformées de façon interne en casts à l'exécution, si bien que, par exemple :  
  
```  
// internally recast into the   
// equivalent safe_cast expression above  
( array<ItemVerb^>^ ) verbList->ToArray( ItemVerb::typeid );   
```  
  
 En revanche, le polymorphisme offrant à la fois un mode actif et un mode passif, il est parfois nécessaire d'exécuter un cast aval simplement pour accéder à l'API non virtuelle d'un sous\-type.  Cela peut se produire, par exemple, avec les membres d'une classe qui souhaitent adresser un type quelconque dans la hiérarchie \(polymorphisme passif utilisé comme mécanisme de transport\) mais pour lesquels on connaît l'instance réelle dans un contexte de programme donné.  Dans ce cas, un contrôle à l'exécution du cast peut représenter une charge mémoire inacceptable.  Si la nouvelle syntaxe doit servir de langage de programmation des systèmes managés, elle doit pouvoir permettre un cast aval à la compilation \(c'est\-à\-dire statique\).  C'est pourquoi l'application de la notation `static_cast` est autorisée à rester un cast aval à la compilation :  
  
```  
// ok: cast performed at compile-time.   
// No run-time check for type correctness  
static_cast< array<ItemVerb^>^>(verbList->ToArray(ItemVerb::typeid));  
```  
  
 Le problème, bien évidemment, est qu'il n'existe aucun moyen de garantir que le programmeur effectuant le `static_cast` sera correct et bien intentionné ; autrement dit, il n'y a aucun moyen de forcer le code managé à être vérifiable.  Cela pose un problème plus urgent dans le cadre du modèle de programme dynamique qu'en natif, mais ce n'est pas suffisant dans un langage de programmation système pour empêcher l'utilisateur de pouvoir basculer entre un cast statique et un cast à l'exécution.  
  
 La nouvelle syntaxe présente toutefois un piège en termes de performance.  En programmation native, il n'existe aucune différence de performances entre l'ancienne notation cast et la nouvelle notation `static_cast`.  Mais dans la nouvelle syntaxe, l'ancienne notation cast s'avère considérablement plus coûteuse que la nouvelle notation `static_cast`.  La raison en est que le compilateur transforme de façon interne l'utilisation de l'ancienne notation en un contrôle à l'exécution qui lève une exception.  En outre, il modifie également le profil d'exécution du code puisqu'il provoque une exception non interceptée qui interrompt l'application \- peut\-être avec raison, mais la même erreur ne provoquerait pas cette exception si la notation `static_cast` était utilisée.  On peut éventuellement considérer que cela contribuera à l'adoption progressive par les utilisateurs de la nouvelle notation.  Mais seulement en cas d'échec car, sinon, le résultat sera que les programmes qui utilisent l'ancienne notation s'exécuteront beaucoup plus lentement sans raison visible, comme dans le cas des pièges de programmation en C suivants :  
  
```  
// pitfall # 1:   
// initialization can remove a temporary class object,   
// assignment cannot  
Matrix m;  
m = another_matrix;  
  
// pitfall # 2: declaration of class objects far from their use  
Matrix m( 2000, 2000 ), n( 2000, 2000 );  
if ( ! mumble ) return;  
```  
  
## Voir aussi  
 [Modification d'ordre général apportée au langage](../dotnet/general-language-changes-cpp-cli.md)   
 [C\-Style Casts with \/clr \(C\+\+\/CLI\)](../windows/c-style-casts-with-clr-cpp-cli.md)   
 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)