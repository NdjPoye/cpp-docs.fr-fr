---
title: "entry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "entry attribute"
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# entry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie une fonction ou une constante exportée dans un module en identifiant le point d'entrée dans la DLL.  
  
## Syntaxe  
  
```  
  
      [ entry(  
   id  
) ]  
```  
  
#### Paramètres  
 `id`  
 L'ID du point d'entrée.  
  
## Notes  
 L'attribut d' **entrée** C\+\+ a les mêmes fonctionnalités que l'attribut d' [entrée](http://msdn.microsoft.com/library/windows/desktop/aa366815) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [idl\_module](../windows/idl-module.md) pour un usage d'exemple d' **entrée**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Attribut `idl_module`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)