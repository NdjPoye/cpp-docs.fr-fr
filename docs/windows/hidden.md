---
title: "hidden | Microsoft Docs"
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
  - "vc-attr.hidden"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hidden attribute"
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hidden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique que l'élément existe mais ne doit pas être affiché dans un navigateur orienté utilisateur.  
  
## Syntaxe  
  
```  
  
[hidden]  
  
```  
  
## Notes  
 L'attribut de **masqué** C\+\+ a les mêmes fonctionnalités que l'attribut de [masqué](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [pouvant être liée](../windows/bindable.md) pour un exemple d'utilisation **masqué**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, **classe**, `struct`, méthode, propriété|  
|**reproductible**|Non|  
|**attributs requis**|**coclasse** \(appliqué à **classe** ou à `struct`\)|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)