---
title: "length_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.length_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "length_is attribute"
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# length_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie le nombre d'éléments de tableau à transmettre.  
  
## Syntaxe  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### Paramètres  
 *expression*  
 Une ou plusieurs expressions de langage C.  Il permet des emplacements vides d'argument.  
  
## Notes  
 L'attribut de **length\_is** C\+\+ a les mêmes fonctionnalités que l'attribut de [length\_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL.  
  
## Exemple  
 Consultez [first\_is](../windows/first-is.md) pour un exemple pour spécifier une section d'un tableau.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Champ dans `struct` ou **union**, paramètre de l'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [max\_is](../windows/max-is.md)   
 [last\_is](../windows/last-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)