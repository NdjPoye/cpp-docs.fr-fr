---
title: "Platform::Collections (espace de noms) | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Collections (espace de noms)"
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Collections (espace de noms)
L'espace de noms Platform::Collection contient les classes `Map`, `MapView`, `Vector` et `VectorView`. Ces classes sont des implémentations concrètes des interfaces correspondantes qui sont définies dans l’espace de noms [Windows::Foundation::Collections](http://go.microsoft.com/fwlink/p/?LinkId=262645). Les types de collection concrets ne sont pas portables à travers l'ABI \(par exemple, lorsqu'un programme JavaScript ou C\# fait appel au composant C\+\+\), mais ils sont implicitement convertibles en leurs types d'interface correspondants. Par exemple, si vous implémentez une méthode publique qui remplit et retourne une collection, utilisez [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) pour implémenter la collection en interne et utilisez [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) comme type de retour. Pour plus d’informations, consultez [Collections](../cppcx/collections-c-cx.md) et [Création de composants Windows Runtime en C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md).  
  
 Vous pouvez construire un Platform::Collections::Vector à partir d'un [std::vector](../Topic/vector%20Class%201.md) et un [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) à partir d'un [std::map](../standard-library/map-class.md).  
  
 En outre, l'espace de noms Platform::Collection assure la prise en charge des itérateurs d'insertion et d'entrée en arrière et des itérateurs `Vector` et `VectorView`.  
  
 Vous devez inclure \(`#include`\) l'en\-tête collection.h pour utiliser les types de l'espace de noms Platform::Collection.  
  
## Syntaxe  
  
```cpp  
  
#include <collection.h>  
using namespace Platform::Collection;  
```  
  
## Membres  
 Cet espace de noms contient les membres ci\-dessous.  
  
|Nom|Description|  
|---------|-----------------|  
|[Platform::Collections::BackInsertIterator, classe](../cppcx/platform-collections-backinsertiterator-class.md)|Représente un itérateur qui insère un élément à la fin d'une collection.|  
|[Platform::Collections::InputIterator, classe](../cppcx/platform-collections-inputiterator-class.md)|Représente un itérateur qui insère un élément au début d'une collection.|  
|[Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)|Représente une collection modifiable de paires clé\/valeur accessibles par une clé. Semblable à [std::map](../standard-library/map-class.md).|  
|[Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md)|Représente une collection en lecture seule de paires clé\/valeur accessibles par une clé.|  
|[Platform::Collections::Vector, classe](../cppcx/platform-collections-vector-class.md)|Représente une séquence d'éléments modifiable. Semblable à [std::vector](../Topic/vector%20Class%201.md).|  
|[Platform::Collections::VectorIterator, classe](../cppcx/platform-collections-vectoriterator-class.md)|Représente un itérateur qui parcourt une collection `Vector`.|  
|[Platform::Collections::VectorView, classe](../cppcx/platform-collections-vectorview-class.md)|Représente une séquence d'éléments en lecture seule.|  
|[Platform::Collections::VectorViewIterator, classe](../cppcx/platform-collections-vectorviewiterator-class.md)|Représente un itérateur qui parcourt une collection `VectorView`.|  
  
## Hiérarchie d'héritage  
 [Espace de noms de plateforme](../cppcx/platform-namespace-c-cx.md)  
  
## Configuration requise  
 **Métadonnées :** platform.winmd  
  
 **Espace de noms :** Platform::Collections  
  
 **Option du compilateur :** \/ZW  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)