---
title: "S&#233;mantique de type valeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__pin (mot clé)"
  - "héritage, types valeur"
  - "interior_ptr (mot clé C++)"
  - "pin_ptr (mot clé C++)"
  - "pointeurs épingle"
  - "fonctions virtuelles, types valeur"
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# S&#233;mantique de type valeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La sémantique des types valeur a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Voici le type valeur canonique simple utilisé dans la spécification d'Extensions managées pour C\+\+ :  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 En Extensions managées, il peut y avoir quatre variantes syntaxiques d'un type valeur \(où les formulaires 2 et 3 sont sémantiquement identiques\) :  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## Appel de méthodes virtuelles héritées  
 `Form (1)` est l'objet de valeur canonique, et il est assez bien compris, sauf si l'on essaie d'appeler une méthode virtuelle héritée telle que `ToString()`.  Par exemple :  
  
```  
v.ToString(); // error!  
```  
  
 Pour appeler cette méthode, le compilateur doit avoir accès à la table virtuelle associée de la classe de base, puisqu'il n'est pas substitué dans `V` Les types valeur représentant un stockage en l'état \(in\-state\) sans un pointeur associé vers sa table virtuelle \(vptr\), il faut que `v` soit converti \(boxed\).  Dans la conception du langage des Extensions managées, la conversion boxing implicite n'est pas prise en charge mais doit être spécifiée explicitement par le programmeur, comme dans  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 La motivation principale de cette conception est d'ordre pédagogique : il s'agit de rendre le mécanisme sous\-jacent visible au programmeur afin qu'il comprenne ce que cela « coûte » de ne pas fournir d'instance dans son type valeur.  Si `V` contenait une instance de `ToString`, les conversions boxing ne seraient pas nécessaires.  
  
 La complexité lexicale de l'opération de boxing explicite de l'objet \(contrairement au coût sous\-jacent de la conversion boxing elle\-même\) disparaît dans la nouvelle syntaxe :  
  
```  
v.ToString(); // new syntax  
```  
  
 cela au risque d'égarer éventuellement le Concepteur de classes quant au coût de n'avoir pas fourni d'instance explicite de la méthode `ToString` dans `V`.  La préférence pour une conversion boxing implicite s'explique de la façon suivante : alors qu'il n'existe habituellement qu'un seul Concepteur de classes, il existe un nombre illimité d'utilisateurs, dont aucun se serait libre de modifier `V` en vue d'éliminer la zone explicite éventuellement onéreuse.  
  
 Les critères servant à déterminer s'il faut ou non fournir une instance de substitution de `ToString` dans une classe de valeur doivent être la fréquence et l'emplacement de ses utilisations.  Si elle est très rarement appelée, il y a bien sûr peu d'intérêt à la définir.  De même, si elle est appelée dans des zones non performantes de l'application, son ajout n'apportera rien de quantifiable aux performances générales de l'application.  Une autre solution consiste à conserver un handle de suivi de la valeur boxed, auquel cas les appels via ce handle ne nécessiteront pas de conversion boxing.  
  
## Il n'y a plus de constructeur par défaut de classe value  
 Une autre différence entre Extensions managées et la nouvelle syntaxe concernant les types valeur est la disparition de la prise en charge du constructeur par défaut.  La raison en est qu'il existe des occasions à l'exécution au cours desquelles le CLR peut créer une instance du type valeur sans appeler le constructeur par défaut associé.  Cela signifie que la tentative, sous Extensions managées, de prendre en charge un constructeur par défaut dans un type valeur ne peut pas être garantie dans la pratique.  Face à cette absence de garantie, il a été jugé préférable d'abandonner totalement cette prise en charge plutôt que de la voir appliquée de façon non déterministe.  
  
 Cela n'est pas aussi grave qu'il peut y paraître au premier abord.  En effet, chaque objet d'un type valeur est automatiquement mis à zéro \(autrement dit, chacun des types est initialisé à sa valeur par défaut\).  En d'autres termes, les membres d'une instance locale ne sont jamais indéfinis.  En ce sens, la perte de la capacité de définir un constructeur trivial par défaut n'en est donc vraiment pas une et cette fonction se révèle finalement plus efficace lorsqu'elle est exécutée par le CLR.  
  
 Le problème se pose lorsqu'un utilisateur d'Extensions managées définit un constructeur par défaut non trivial.  Celui\-ci ne possède aucun mappage vers la nouvelle syntaxe.  Le code au sein du constructeur devra migrer vers une méthode d'initialisation nommée qui devra ensuite être appelée explicitement par l'utilisateur.  
  
 La déclaration d'un objet de type valeur dans la nouvelle syntaxe est par ailleurs inchangée.  L'inconvénient de tout ceci est que les types valeur sont mal adaptés à l'habillage de types natifs, cela pour les raisons suivantes :  
  
-   Il n'y a pas de prise en charge du destructeur dans un type valeur.  En d'autres termes, il y a aucune façon d'automatiser une série d'actions déclenchée par la fin de la durée de vie d'un objet.  
  
-   Une classe native ne peut être contenue dans un type managé qu'en tant que pointeur ultérieurement alloué sur le tas natif.  
  
 On pourrait souhaiter habiller une petite classe native dans un type valeur plutôt que dans un type référence afin d'éviter une double allocation de tas : le tas natif pour stocker le type natif, et le tas CLR pour stocker le wrapper managé.  Habiller une classe native dans un type valeur permet d'éviter le tas managé, mais n'offre aucun moyen d'automatiser la récupération de la mémoire du tas natif.  Les types référence sont le seul type managé utilisable dans lequel habiller des classes natives non triviales.  
  
## Pointeurs intérieurs  
 Les `Form (2)` et `Form (3)` ci\-dessus peuvent presque tout adresser dans ce monde ou dans l'autre \(c'est\-à\-dire tout ce qui est géré ou natif\).  Par exemple, tout ce qui suit est donc autorisé dans les Extensions managées :  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
V *pv = 0;  // Form (2)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0;  // Form (4)  
  
R* r;  
  
pv = &v;            // address a value type on the stack  
pv = __nogc new V;  // address a value type on native heap  
pv = pvgc;          // we are not sure what this addresses  
pv = pvbx;          // address a boxed value type on managed heap  
pv = &r->vr;        // an interior pointer to value type within a  
                    //    reference type on the managed heap  
```  
  
 Ainsi, un `V*` peut adresser un emplacement dans un bloc local \(et par conséquent rester non résolu\), au niveau de la portée globale, dans le tas natif \(par exemple, si l'objet qu'il adresse a déjà été supprimé\), dans le tas CLR \(il sera alors suivi s'il doit être déplacé pendant l'opération de garbage collection\), et à l'intérieur d'un objet de référence sur le tas CLR \(un pointeur intérieur, car tel est son nom, est également suivi de façon transparente\).  
  
 En Extensions managées, il n'y a aucun moyen de séparer les aspects natifs d'un `V*` ; il est donc traité comme son inclusif, ce qui permet de lui faire adresser un objet ou un sous\-objet sur le tas managé.  
  
 Dans la nouvelle syntaxe, un pointeur de type valeur se présente sous deux types : `V*`, qui se limite aux emplacements de tas non CLR, et le pointeur intérieur, `interior_ptr<V>`, qui permet, sans que cela soit obligatoire, d'avoir une adresse dans le tas managé.  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 `Form (2)` et `Form (3)` des Extensions managées mappent dans `interior_ptr<V>`.  `Form (4)` est un handle de suivi.  Il adresse l'objet entier sous forme boxed dans le tas managé.  Il se traduit dans la nouvelle syntaxe par un `V^`  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 Les déclarations suivantes en Extensions managées mappent toutes vers des pointeurs intérieurs dans la nouvelle syntaxe. \(Il s'agit de types valeur dans l'espace de noms `System`\).  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 Les types intégrés ne sont pas considérés comme des types managés, bien qu'ils servent d'alias aux types dans l'espace de noms `System`.  Les mappages suivants restent vrais entre Extensions managées et la nouvelle syntaxe :  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 Lorsqu'il faut traduire un `V*` dans un programme existant, la stratégie la plus conservatrice le transforme toujours en `interior_ptr<V>`.  C'est du moins ainsi que le traitait Extensions managées.  Dans la nouvelle syntaxe, le programmeur a la possibilité de restreindre un type valeur à des adresses de tas non managé en spécifiant `V*` plutôt qu'un pointeur intérieur.  Si, en traduisant votre programme, vous pouvez procéder à une fermeture transitive de toutes ses utilisations et vérifier qu'aucune adresse assignée ne se trouve dans le tas managé, alors, vous pouvez sans problème le laisser sous la forme `V*`.  
  
## Pointeurs épingle  
 Le garbage collector peut éventuellement déplacer les objets qui résident sur le tas du CLR vers des emplacements différents dans le tas, en général lors d'une phase de compactage.  Ce déplacement ne pose aucun problème aux handles de suivi, aux références de suivi et aux pointeurs intérieurs, qui mettent à jour ces entités de façon transparente.  Il devient toutefois problématique si l'utilisateur a passé l'adresse d'un objet sur le tas CLR hors de l'environnement d'exécution.  Dans ce cas, le déplacement volatil de l'objet est susceptible de provoquer une défaillance d'exécution.  Pour empêcher que de tels objets ne soient déplacés, il faut les épingler localement sur leur emplacement pour toute l'étendue de leur utilisation externe.  
  
 En Extensions managées, un *pointeur épingle* se déclare en qualifiant une déclaration de pointeur avec le mot clé `__pin`.  Voici un exemple légèrement modifié issu de la spécification d'Extensions managées :  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // …  
};  
```  
  
 Dans la nouvelle conception de langage, un pointeur épingle se déclare avec une syntaxe analogue à celle d'un pointeur intérieur.  
  
```  
ref struct H  
{  
public:  
   int j;  
};  
  
int main()  
{  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
  
   // …  
}  
```  
  
 Un pointeur épingle, dans la nouvelle syntaxe, est un cas spécial de pointeur intérieur.  Les contraintes d'origine continuent de s'appliquer à un pointeur épingle.  Par exemple, celui\-ci ne peut pas être utilisé comme paramètre ou type de retour d'une méthode ; au contraire, il ne peut être déclaré que sur un objet local.  Plusieurs contraintes supplémentaires ont cependant été ajoutées dans la nouvelle syntaxe.  
  
 La valeur par défaut d'un pointeur épingle est `nullptr`, et non `0`.  Un `pin_ptr<>` ne peut pas être initialisé ou recevoir la valeur `0`.  Toutes les assignations de `0` dans le code existant devront être transformées en `nullptr`.  
  
 Sous Extensions managées, un pointeur épingle était autorisé à adresser un objet entier, comme dans l'exemple suivant emprunté à la spécification d'Extensions managées :  
  
```  
__gc class G {  
public:  
   void incr(int* pi) { pi += 1; }  
};  
__gc struct H { int j; };  
void f( G * g ) {  
   H __pin * pH = new H;     
   g->incr(& pH -> j);     
};  
```  
  
 Dans la nouvelle syntaxe, l'épinglage de l'objet entier retourné par l'expression `new` n'est pas pris en charge.  L'adresse du membre intérieur doit au contraire être épinglée.  Par exemple :  
  
```  
ref class G {  
public:  
   void incr(int* pi) { *pi += 1; }  
};  
ref struct H { int j; };  
void f( G^ g ) {  
   H ^ph = gcnew H;  
   Console::WriteLine(ph->j);  
   pin_ptr<int> pj = &ph->j;  
   g->incr(  pj );  
   Console::WriteLine(ph->j);  
}  
```  
  
## Voir aussi  
 [Types valeur et leurs comportements \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)   
 [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)