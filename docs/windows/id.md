---
title: "id | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "id attribute"
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# id
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

spécifie un paramètre d' `dispid` pour une fonction membre \(une propriété ou une méthode, dans une interface ou dispinterface\).  
  
## Syntaxe  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### Paramètres  
 `dispid`  
 L'ID de dispatch de la méthode d'interface.  
  
## Notes  
 L'attribut d' **identificateur** C\+\+ a les mêmes fonctionnalités que l'attribut d' [identificateur](http://msdn.microsoft.com/library/windows/desktop/aa367040) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [pouvant être liée](../windows/bindable.md) pour un exemple d'utilisation **identificateur**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [in](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)