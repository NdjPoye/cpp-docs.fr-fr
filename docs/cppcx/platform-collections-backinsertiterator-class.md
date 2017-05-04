---
title: "Platform::Collections::BackInsertIterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator (classe)"
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::BackInsertIterator, classe
Représente un itérateur qui ne remplace pas les éléments mais les insère dans le back end d'une collection séquentielle.  
  
## Syntaxe  
  
```  
template <  
   typename T  
>  
class BackInsertIterator : public ::std::iterator< ::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### Paramètres  
 `T`  
 Type d'élément de la collection active.  
  
## Notes  
 La classe BackInsertIterator implémente les règles requises par la [back\_insert\_iterator, classe](../standard-library/back-insert-iterator-class.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[BackInsertIterator::BackInsertIterator \(constructeur\)](../cppcx/backinsertiterator-backinsertiterator-constructor.md)|Initialise une nouvelle instance de la classe BackInsertIterator.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[BackInsertIterator::operator\* \(opérateur\)](../cppcx/backinsertiterator-operator-dereference-operator.md)|Extrait une référence au BackInsertIterator actif.|  
|[BackInsertIterator::operator\+\+ \(opérateur\)](../cppcx/backinsertiterator-operator-increment-operator.md)|Retourne une référence au BackInsertIterator actif. L'itérateur est pas modifié.|  
|[BackInsertIterator::operator\= \(opérateur\)](../cppcx/backinsertiterator-operator-assign-operator.md)|Ajoute l'objet spécifié à la fin de la collection séquentielle en cours.|  
  
## Hiérarchie d'héritage  
 `BackInsertIterator`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)