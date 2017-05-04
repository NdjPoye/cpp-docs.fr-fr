---
title: "Platform::Collections::VectorIterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator (classe)"
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::VectorIterator, classe
Fournit un itérateur Standard Template Library pour les objets dérivés de l'interface IVector [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 VectorIterator est un itérateur de proxy qui stocke des éléments de type VectorProxy\<T\>. Toutefois, l'objet proxy n'est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
class VectorIterator;  
```  
  
#### Paramètres  
 `T`  
 Nom de type de la classe de modèle VectorIterator.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`difference_type`|Différence de pointeur \(ptrdiff\_t\).|  
|`iterator_category`|Catégorie d'un itérateur à accès aléatoire \(::std::random\_access\_iterator\_tag\).|  
|`pointer`|Pointeur vers un type interne Platform::Collections::Details::VectorProxy\<T\> qui est requis pour l'implémentation de VectorIterator.|  
|`reference`|Référence à un type interne Platform::Collections::Details::VectorProxy\<T\> qui est requis pour l'implémentation de VectorIterator.|  
|`value_type`|Nom de type `T`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[VectorIterator::VectorIterator \(constructeur\)](../cppcx/vectoriterator-vectoriterator-constructor.md)|Initialise une nouvelle instance de la classe VectorIterator.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[VectorIterator::operator\- \(opérateur\)](../cppcx/vectoriterator-operator-minus-operator.md)|Soustrait un nombre spécifié d'éléments de l'itérateur actuel en cédant un nouvel itérateur, ou un itérateur spécifié de l'itérateur actuel en cédant le nombre d'éléments entre les itérateurs.|  
|[VectorIterator::operator\-\- \(opérateur\)](../cppcx/vectoriterator-operator-decrement-operator.md)|Décrémente le VectorIterator actif.|  
|[VectorIterator::operator\!\= \(opérateur\)](../cppcx/vectoriterator-operator-inequality-operator.md)|Indique si le VectorIterator actif n'est pas égal à un VectorIterator spécifié.|  
|[VectorIterator::operator\* \(opérateur\)](../cppcx/vectoriterator-operator-dereference-operator.md)|Récupère une référence à l'élément spécifié par le VectorIterator actif.|  
|[VectorIterator::operatorOperator](../cppcx/vectoriterator-operatoroperator.md)|Récupère une référence à l'élément qui est un décalage spécifié à partir de l'objet VectorIterator actuel.|  
|[\(DELETE\) VectorIterator::operator\+ \(opérateur\)](http://msdn.microsoft.com/fr-fr/b0b1af2c-e2a8-4876-99dc-7351bfc46ce4)|Retourne un VectorIterator qui référence l'élément spécifié au décalage spécifié à partir du VectorIterator spécifié.|  
|[VectorIterator::operator\+\+ \(opérateur\)](../cppcx/vectoriterator-operator-increment-operator.md)|Incrémente le VectorIterator actif.|  
|[VectorIterator::operator\+\= \(opérateur\)](../cppcx/vectoriterator-operator-plus-assign-operator.md)|Incrémente le VectorIterator actif du décalage spécifié.|  
|[VectorIterator::operator\< \(opérateur\)](../cppcx/vectoriterator-operator-less-than-operator.md)|Indique si le VectorIterator actuel est inférieur au VectorIterator spécifié.|  
|[VectorIterator::operator\<\= \(opérateur\)](../cppcx/vectoriterator-operator-less-than-or-equals-operator.md)|Indique si l'objet VectorIterator actuel est inférieur ou égal à un objet VectorIterator spécifié.|  
|[VectorIterator::operator\-\= \(opérateur\)](../cppcx/vectoriterator-operator-subtract-assign-operator.md)|Décrémente l'objet VectorIterator actuel du décalage spécifié.|  
|[VectorIterator::operator\=\= \(opérateur\)](../cppcx/vectoriterator-operator-equality-operator.md)|Indique si l'objet VectorIterator actuel est égal à un objet VectorIterator spécifié.|  
|[VectorIterator::operator\> \(opérateur\)](../cppcx/vectoriterator-operator-greater-than-operator.md)|Indique si le VectorIterator actif est supérieur au VectorIterator spécifié.|  
|[VectorIterator::operator\-\> \(opérateur\)](../cppcx/vectoriterator-operator-arrow-operator.md)|Récupère l'adresse de l'élément référencé par le VectorIterator actif.|  
|[VectorIterator::operator\>\= \(opérateur\)](../cppcx/vectoriterator-operator-greater-than-or-equal-operator.md)|Indique si le VectorIterator actif est supérieur ou égal à un VectorIterator spécifié.|  
  
## Hiérarchie d'héritage  
 `VectorIterator`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)