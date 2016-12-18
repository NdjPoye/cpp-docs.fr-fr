---
title: "pointer_default | Microsoft Docs"
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
  - "vc-attr.pointer_default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_default attribute"
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pointer_default
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie l'attribut par défaut de pointeur pour tous les pointeurs, à l'exception de les pointeurs de niveau supérieur qui apparaissent dans les listes de paramètres.  
  
## Syntaxe  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### Paramètres  
 *correspondante*  
 une valeur qui décrit le type pointeur : **prentice**, `ref`, ou **unique**.  
  
## Notes  
 L'attribut de **pointer\_default** C\+\+ a les mêmes fonctionnalités que l'attribut de [pointer\_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [defaultvalue](../windows/defaultvalue.md) pour un usage d'exemple de **pointer\_default**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)