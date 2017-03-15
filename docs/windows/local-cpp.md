---
title: "local (C++) | Microsoft Docs"
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
  - "vc-attr.local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "local attribute"
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# local (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'il est utilisé dans l'en\-tête d'interface, vous permet d'utiliser le compilateur MIDL comme générateur d'en\-tête.  Lorsqu'il est utilisé dans une fonction spécifique, indique une procédure locale pour laquelle un stub n'est généré.  
  
## Syntaxe  
  
```  
  
[local]  
  
```  
  
## Notes  
 L'attribut d' `local` C\+\+ a les mêmes fonctionnalités que l'attribut de [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL.  
  
## Exemple  
 Consultez [call\_as](../windows/call-as.md) pour un exemple d'utilisation `local`.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|**dispinterface**|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [call\_as](../windows/call-as.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)