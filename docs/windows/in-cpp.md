---
title: "in (C++) | Microsoft Docs"
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
  - "vc-attr.in"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "in attribute"
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# in (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique qu'un paramètre doit être passé de la procédure appelante jusqu'à la procédure appelée.  
  
## Syntaxe  
  
```  
  
[in]  
  
```  
  
## Notes  
 L'attribut de **dans** C\+\+ a les mêmes fonctionnalités que l'attribut de [dans](http://msdn.microsoft.com/library/windows/desktop/aa367051) MIDL.  
  
## Exemple  
 Consultez [pouvant être liée](../windows/bindable.md) pour un exemple d'utilisation **dans**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|paramètre d'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|**retval**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [id](../windows/id.md)   
 [out](../windows/out-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)