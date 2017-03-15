---
title: "size_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.size_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_is attribute"
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# size_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifiez la taille de la mémoire allouée pour des pointeurs dimensionnés, les pointeurs dimensionnés aux pointeurs dimensionnés, et unique ou aux tableaux multidimensionnels.  
  
## Syntaxe  
  
```  
  
      [ size_is(  
   "expression"  
) ]  
```  
  
#### Paramètres  
 *expression*  
 La taille de la mémoire allouée pour les pointeurs dimensionnés.  
  
## Notes  
 L'attribut de **size\_is** C\+\+ a les mêmes fonctionnalités que l'attribut de [size\_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [first\_is](../windows/first-is.md) pour un exemple pour spécifier une section d'un tableau.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Champ dans `struct` ou **union**, paramètre de l'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|**max\_is**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [max\_is](../windows/max-is.md)   
 [length\_is](../windows/length-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)