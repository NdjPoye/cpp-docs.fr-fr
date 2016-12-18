---
title: "Gestion de la dur&#233;e de vie et des ressources de l&#39;objet (Modern C++) | Microsoft Docs"
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
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion de la dur&#233;e de vie et des ressources de l&#39;objet (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrairement aux langages managés, C\+\+ ne possède aucun nettoyage \(GC\), qui libère automatiquement les ressources mémoire qui ne sont plus utilisées au cours de l'exécution du programme.  En C\+\+, la gestion des ressources est directement liée à la durée de vie des objets.  Ce document explique les facteurs qui affectent la durée de vie des objets en C\+\+ et comment les gérer.  
  
 C\+\+ n'a pas de GC principalement car il ne gère pas les ressources en mémoire.  Seuls les destructeurs déterministes comme ceux en C\+\+ peuvent gérer de manière identique les ressources mémoire et non\-mémoire.  Le GC a également d'autres problèmes, comme une surcharge plus élevée de la mémoire et de la consommation processeur, et un aspect local.  L'universalité est un problème fondamental qui ne peut pas être atténué via des optimisations intelligentes.  
  
## Concepts  
 Un point essentiel de la gestion de la durée de vie des objets est l'encapsulation \- la valeur à l'objet n'a pas besoin de connaître les ressources que possède l'objet, ou comment les supprimer à partir de celles\-ci, ou même s'il possède la moindre ressource.  Elle doit simplement détruire l'objet.  Le language principale C\+\+ est conçu pour vous assurer que les objets sont détruits aux moments appropriés., c. \- à\-d., lorsque les blocs sont quittés, dans l'ordre inverse de la construction.  Lorsqu'un objet est détruit, ses bases et membres sont détruits dans un ordre précis.  La langue détruit automatiquement les objets, à moins que vous ne fassiez des opérations particulières telles que l'allocation des segments ou le positionnement nouveau.  Par exemple, des [pointeurs à puce](../cpp/smart-pointers-modern-cpp.md) telles que des conteneurs de `unique_ptr` et `shared_ptr`, et Standard TEMPLATE Library \(STL\) de la `vector`, encapsulent `new`\/`delete` et `new[]`\/`delete[]` dans des objets, qui ont des destructeurs.  C'est pourquoi il est si important d'utiliser les pointeurs intelligents et les conteneurs STL.  
  
 Un autre concept important dans la gestion de la durée de vie : les destructeurs.  Les destructeurs encapsulent la version de la ressource.  \(La mnémonique utilisée couramment est RRID, La libération de la ressource signifie sa destruction.\)  Une ressource est quelque chose que vous obtenez du « système » et que vous devez rendre plus tard.  La mémoire est la ressource la plus courante, mais il existe également des fichiers, des sockets, des textures, et d'autres ressources en mémoire. Etre « propriétaire » d'une ressource signifie que vous pouvez utiliser lorsque vous avez besoin mais vous devez également la libérer lorsque vous avez terminé avec elle.  Lorsqu'un objet est détruit, le destructeur libère les ressources dont il était propriétaire.  
  
 Le concept final est le DAG \(Graphique dirigé acyclique\).  La structure de la propriété dans un programme forme un DAG.  Aucun objet ne peut se posséder soi\-même\- non seulement c'est impossible mais cela n'aurait également pas de sens en soi.  Mais deux objets peuvent partager la propriété d'un troisième objet.  Plusieurs types de liens sont possibles dans un DAG comme suit : A est un membre de B \(B possède 1\), C stockes un `vector<D>` \(C possède chaque élément de D\), E stockes un `shared_ptr<F>` \(E partage la propriété de F, éventuellement d'autres objets\), etc.  Tant qu'il n'y a pas de cycles et que chaque lien dans le DAG est représenté par un objet qui possède un destructeur \(au lieu d'un pointeur brut, d'un handle, ou de tout autre mécanisme\), alors d'éventuelles fuites de ressources sont impossibles car le langage les prévient.  Les ressources sont libérées dès qu'elles ne sont plus nécessaires, sans exécution du garbage collector.  Le suivi de la durée de vie est libre de toute surcharge pour la place de pile, les bases, les membres, les cas associés, et peu coûteuse pour `shared_ptr`.  
  
### Durée de vie basée sur un tas  
 Pour la durée de vie d'un l'objet tas, utilisez des [pointeurs à puce](../cpp/smart-pointers-modern-cpp.md).  Utilisez `shared_ptr` et `make_shared` en tant que pointeur et allocateur par défaut.  Utilisez `weak_ptr` pour désactiver des cycles, effectuer la mise en cache, et observer des objets sans affecter ou présumer quoique ce soit sur leurs durées de vie.  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 Utilisez `unique_ptr` pour une propriété unique, par exemple, dans l'idiome *de pimpl*. \(Consultez [Pimpl pour l'encapsulation au moment de la compilation](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).\) Faites d'un `unique_ptr` la cible primaire de toutes les expressions explicites de `new`.  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 Vous pouvez utiliser les pointeurs bruts pour une absence de propriété et une observation.  Un pointeur non propriétaire peut se balancer, mais il ne peut pas fuir.  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 Lorsque l'optimisation des performances est requise, vous devrez peut\-être utiliser des poiteurs propriétaires *correctement encapsulé* et des appels explicites à supprimer.  Un exemple est lorsque vous implémentez votre propre structure de données de bas niveau.  
  
### Durée de vie basée sur la pile  
 En C\+\+ moderne, *la portée basée sur la pile* est une puissante façon d'écrire du code solide car elle combine *la durée de vie de pile* automatique et *la durée de vie de l'attribut* avec une grande efficacité \- le suivi de la durée de vie est essentiellement libre de toute surcharge.  La durée de vie de l'objet heap requiert une gestion manuelle diligente et peut être la source de fuites et d'inefficacités des ressources, surtout si vous utilisez des pointeurs bruts.  Considérez ce code, qui illustre la portée basée sur la pile :  
  
```cpp  
class widget {  
private:  
  gadget g;   // lifetime automatically tied to enclosing object  
public:  
  void draw();  
};  
  
void functionUsingWidget () {  
  widget w;   // lifetime automatically tied to enclosing scope  
              // constructs w, including the w.g gadget member  
  …  
  w.draw();  
  …  
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
  
```  
  
 Utilisez la durée de vie statique avec parcimonie \(statique globale, fonction statique locale\) car des problèmes peuvent survenir.  Que se produit\-il lorsque le constructeur d'un objet global lève une exception ?  En général, l'application échoue d'une manière qui rend le débogage difficile.  La commande de construction pose problème pour les objets statiques de durée de vie, et n'est pas sécurisé vis à vis de la concurrence.  Non seulement la construction d'un objet est un problème, mais les commandes de destruction peuvent être complexes, surtout lorsque le polymorphisme est implicite.  Même si votre objet ou variable n'est pas polymorphe et n'a pas de classement de construction ou de destruction complexes, il y a toujours la question de la sécurité du thread vis à vis de la concurrence.  Une application multithread ne peut pas sans risque modifier les données des objets statiques sans avoir un stockage local des threads, des verrous de ressources, et des précautions spéciales.  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)