---
title: "Platform::Collections::VectorViewIterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator (classe)"
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Collections::VectorViewIterator, classe
Fournit un itérateur STL \(Standard Template Library\) pour les objets dérivés de l’interface [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IVectorView`.  
  
 `ViewVectorIterator` est un itérateur de proxy qui stocke des éléments de type `VectorProxy<T>`. Toutefois, l'objet proxy n'est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
class VectorViewIterator;  
```  
  
#### Paramètres  
 `T`  
 Typename de la classe de modèle VectorViewIterator.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`difference_type`|Différence de pointeur \(ptrdiff\_t\).|  
|`iterator_category`|Catégorie d'un itérateur à accès aléatoire \(::std::random\_access\_iterator\_tag\).|  
|`pointer`|Pointeur vers un type interne requis pour l'implémentation de VectorViewIterator.|  
|`reference`|Référence à un type interne requis pour l'implémentation de VectorViewIterator.|  
|`value_type`|Nom de type `T`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[VectorViewIterator::VectorViewIterator \(constructeur\)](../cppcx/vectorviewiterator-vectorviewiterator-constructor.md)|Initialise une nouvelle instance de la classe VectorViewIterator.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[VectorViewIterator::operator\- \(opérateur\)](../cppcx/vectorviewiterator-operator-minus-operator.md)|Soustrait un nombre spécifié d'éléments de l'itérateur actuel en cédant un nouvel itérateur, ou un itérateur spécifié de l'itérateur actuel en cédant le nombre d'éléments entre les itérateurs.|  
|[VectorViewIterator::operator\-\- \(opérateur\)](../cppcx/vectorviewiterator-operator-decrement-operator.md)|Décrémente le VectorViewIterator actif.|  
|[VectorViewIterator::operator\!\= \(opérateur\)](../cppcx/vectorviewiterator-operator-inequality-operator.md)|Indique si le VectorViewIterator actuel n'est pas égal à un VectorViewIterator spécifié.|  
|[VectorViewIterator::operator\* \(opérateur\)](../cppcx/vectorviewiterator-operator-dereference-operator.md)|Récupère une référence à l'élément spécifié par le VectorViewIterator actif.|  
|[VectorViewIterator::operator, opérateur](../cppcx/vectorviewiterator-operatoroperator.md)|Extrait une référence à l'élément qui est un offset spécifié de l'objet VectorViewIterator actuel.|  
|[VectorViewIterator::operator\+ \(opérateur\)](../cppcx/vectorviewiterator-operator-plus-operator.md)|Retourne un VectorIterator qui référence l'élément au décalage spécifié à partir du VectorViewIterator spécifié.|  
|[VectorViewIterator::operator\+\+ \(opérateur\)](../cppcx/vectorviewiterator-operator-increment-operator.md)|Incrémente l'objet VectorViewIterator actuel.|  
|[VectorViewIterator::operator\+\= \(opérateur\)](../cppcx/vectorviewiterator-operator-plus-assign-operator.md)|Incrémente le VectorViewIterator actuel par le décalage spécifié.|  
|[VectorViewIterator::operator\< \(opérateur\)](../cppcx/vectorviewiterator-operator-less-than-operator.md)|Indique si le VectorViewIterator actif est inférieur à un VectorViewIterator spécifié.|  
|[VectorViewIterator::operator\<\= \(opérateur\)](../cppcx/vectorviewiterator-operator-less-than-or-equals-operator.md)|Indique si le VectorViewIterator actif est inférieur ou égal à un VectorViewIterator spécifié.|  
|[VectorViewIterator::operator\-\= \(opérateur\)](../cppcx/vectorviewiterator-operator-subtract-assign-operator.md)|Décrémente le VectorViewIterator actif du décalage spécifié.|  
|[VectorViewIterator::operator\=\= \(opérateur\)](../cppcx/vectorviewiterator-operator-equality-operator.md)|Indique si le VectorViewIterator actif est égal à un VectorViewIterator spécifié.|  
|[VectorViewIterator::operator\> \(opérateur\)](../cppcx/vectorviewiterator-operator-greater-than-operator.md)|Indique si le VectorViewIterator actif est supérieur à un VectorViewIterator spécifié.|  
|[VectorViewIterator::operator\-\> \(opérateur\)](../cppcx/vectorviewiterator-operator-arrow-operator.md)|Récupère l'adresse de l'élément référencé par le VectorViewIterator actif.|  
|[VectorViewIterator::operator\>\= \(opérateur\)](../cppcx/vectorviewiterator-operator-greater-than-or-equals-operator.md)|Indique si le VectorViewIterator actif est supérieur ou égal à un VectorViewIterator spécifié.|  
  
## Hiérarchie d'héritage  
 `VectorViewIterator`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)