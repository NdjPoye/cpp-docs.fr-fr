---
title: "Exemple de conteneurs, classe | Microsoft Docs"
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
  - "classes de conteneur"
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exemple de conteneurs, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Cette rubrique est dans la documentation Visual C++ comme un exemple de conteneurs utilisés dans la bibliothèque C++ Standard ne fonctionne pas. Pour plus d’informations, consultez [conteneurs STL](../standard-library/stl-containers.md).  
  
 Décrit un objet qui contrôle une séquence de longueur variable d’éléments, généralement de type **Ty**. La séquence est stockée de différentes manières, selon le conteneur réel.  
  
 Une fonction de constructeur ou un membre de conteneur peut trouver l’occasion pour appeler le constructeur **Ty**(**const Ty &**) ou la fonction **Ty::operator =**(**const Ty &**). Si un tel appel lève une exception, l’objet conteneur est tenu de maintenir son intégrité et de lever à nouveau une exception d’emblée. Vous pouvez en toute sécurité échange, affecter à effacer ou de détruire un objet conteneur après que elle lève l’une de ces exceptions. En général, toutefois, vous pouvez sinon prédire l’état de la séquence contrôlée par l’objet conteneur.  
  
 Quelques avertissements supplémentaires :  
  
-   Si l’expression **~ Ty** lève une exception, l’état résultant de l’objet de conteneur n’est pas défini.  
  
-   Si le conteneur stocke un objet allocateur *al*, et *al* lève une exception autre que suite à un appel à *al***.allocate**, l’état résultant de l’objet de conteneur n’est pas défini.  
  
-   Si le conteneur stocke un objet de fonction *comp*, afin de déterminer l’ordre de la séquence contrôlée, et *comp* lève une exception de tout type, l’état résultant de l’objet de conteneur n’est pas défini.  
  
 Les classes de conteneur définis par STL satisfont plusieurs exigences supplémentaires, comme décrit dans les paragraphes suivants.  
  
 Classe de conteneur du modèle [liste](../standard-library/list-class.md) fournit un comportement déterministe et utile, même en cas d’exceptions décrites ci-dessus. Par exemple, si une exception est levée lors de l’insertion d’un ou plusieurs éléments, le conteneur n’est pas modifié et l’exception est levée de nouveau.  
  
 Pour *tous les* les classes de conteneur définis par STL, si une exception est levée pendant les appels aux fonctions membres suivantes :  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 le conteneur n’est pas modifié et l’exception est levée de nouveau.  
  
 Pour *tous les* les classes de conteneur définis par STL, aucune exception n’est levée pendant les appels aux fonctions membres suivantes :  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 La fonction membre [Effacer](../standard-library/container-class-erase.md) lève une exception uniquement si une opération de copie (construction attribution ou de copie) lève une exception.  
  
 En outre, aucune exception n’est levée lors de la copie d’un itérateur retourné par une fonction membre.  
  
 La fonction membre [échange](../standard-library/container-class-swap.md) rend les promesses supplémentaires pour *tous les* classes de conteneur définis par STL :  
  
-   La fonction membre lève une exception uniquement si le conteneur stocke un al objet allocateur, et `al` lève une exception lors de la copier.  
  
-   Références, pointeurs et itérateurs qui désignent les éléments des séquences contrôlées permutés restent valides.  
  
 Un objet d’une classe de conteneur défini par STL alloue et libère du stockage pour la séquence qu’il contrôle via un objet stocké de type `Alloc`, qui est généralement un paramètre de modèle. Un tel objet allocateur doit avoir la même interface externe en tant qu’objet de classe **allocateur \< Ty>**. En particulier, `Alloc` doit être du même type que **Alloc::rebind \< value_type > :: autres**  
  
 Pour *tous les* classes de conteneur définis par STL, la fonction membre **get_allocator Alloc const ;** retourne une copie de l’objet allocateur stocké. Notez que l’objet allocateur stocké est *pas* copié lorsque l’objet conteneur est assigné. Tous les constructeurs initialisent la valeur stockée dans **allocateur**, à `Alloc` Si le constructeur ne contient aucun paramètre d’allocateur.  
  
 Selon la norme C++, une classe de conteneur définie par STL peut supposer que :  
  
-   Tous les objets de classe `Alloc` comparaison égale.  
  
-   Type **Alloc::const_pointer** est identique à **Ty const \***.  
  
-   Type **Alloc::const_reference** est identique à **const Ty &**.  
  
-   Type **Alloc::pointer** est identique à **Ty \***.  
  
-   Type **Alloc::reference** est identique à **Ty &**.  
  
 Dans cette implémentation, cependant, les conteneurs ne faites pas ces suppositions de simplification. Par conséquent, ils fonctionnent correctement avec les objets allocateurs qui sont plus ambitieux :  
  
-   Tous les objets de la classe `Alloc` est inutile de comparaison égale. (Vous pouvez conserver plusieurs pools de stockage.)  
  
-   Type **Alloc::const_pointer** sans devoir être le même que **Ty const \***. (Un pointeur const peut être une classe.)  
  
-   Type **Alloc::pointer** sans devoir être le même que **Ty \***. (Un pointeur peut être une classe.)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête**\< : exemple de conteneur>  
  
## <a name="see-also"></a>Voir aussi  
 [\< exemple (conteneur)>](../standard-library/sample-container.md)

