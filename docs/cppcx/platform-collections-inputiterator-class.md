---
title: "Platform::Collections::InputIterator, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator (classe)"
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::InputIterator, classe
Fournit un InputIterator de bibliothèque STL \(Standard Template Library\) pour les collections dérivées de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
## Syntaxe  
  
```  
template <  
   typename X  
>  
class InputIterator;  
```  
  
#### Paramètres  
 `X`  
 Nom de type de la classe de modèle InputIterator.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`difference_type`|Différence de pointeur \(ptrdiff\_t\).|  
|`iterator_category`|Catégorie d’un itérateur d’entrée \(:: std::input\_iterator\_tag\).|  
|`pointer`|Pointeur vers un `const` `X`|  
|`reference`|Référence à un `const` `X`|  
|`value_type`|Nom de type `X`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[InputIterator::InputIterator \(constructeur\)](../cppcx/inputiterator-inputiterator-constructor.md)|Initialise une nouvelle instance de la classe InputIterator.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[InputIterator::operator\!\= \(opérateur\)](../cppcx/inputiterator-operator-inequality-operator.md)|Indique si l'InputIterator actif n'est pas égal à un InputIterator spécifié.|  
|[InputIterator::operator\* \(opérateur\)](../cppcx/inputiterator-operator-decrementoperator.md)|Récupère une référence à l’élément spécifié par l’InputIterator actif.|  
|[InputIterator::operator\+\+ \(opérateur\)](../cppcx/inputiterator-operator-increment-operator.md)|Incrémente l'objet InputIterator actuel.|  
|[InputIterator::operator\=\= \(opérateur\)](../cppcx/inputiterator-operator-equality-operator.md)|Indique si l'InputIterator actif est égal à un InputIterator spécifié.|  
|[InputIterator::operator\-\> \(opérateur\)](../cppcx/inputiterator-operator-arrow-operator.md)|Récupère l’adresse de l’élément référencé par l’InputIterator actif.|  
  
## Hiérarchie d'héritage  
 `InputIterator`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)