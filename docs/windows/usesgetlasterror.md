---
title: "usesgetlasterror | Microsoft Docs"
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
  - "vc-attr.usesgetlasterror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "usesgetlasterror attribute"
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# usesgetlasterror
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique l'appelant que s'il existe une erreur en appelant cette fonction, l'appelant peut ensuite appeler `GetLastError` pour extraire le code d'erreur.  
  
## Syntaxe  
  
```  
  
[usesgetlasterror]  
  
```  
  
## Notes  
 L'attribut d' **usesgetlasterror** C\+\+ a les mêmes fonctionnalités que l'attribut d' [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL.  
  
## Exemple  
 Consultez l'exemple d' [idl\_module](../windows/idl-module.md) pour un exemple d'utilisation **usesgetlasterror**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|attribut de**module**|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)