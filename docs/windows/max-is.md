---
title: "max_is | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.max_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_is attribute"
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# max_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique la valeur maximale pour un index non valide de tableau.  
  
## Syntaxe  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### Paramètres  
 *expression*  
 Une ou plusieurs expressions de langage C.  Il permet des emplacements vides d'argument.  
  
## Notes  
 L'attribut de **max\_is** C\+\+ a les mêmes fonctionnalités que l'attribut de [max\_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Champ dans `struct` ou **union**, paramètre de l'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|**size\_is**|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Exemple  
 Consultez [first\_is](../windows/first-is.md) pour un exemple pour spécifier une section d'un tableau.  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [length\_is](../windows/length-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)