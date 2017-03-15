---
title: "object (C++) | Microsoft Docs"
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
  - "vc-attr.object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "object attribute"
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# object (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

identifie une interface personnalisée.  
  
## Syntaxe  
  
```  
  
[object]  
  
```  
  
## Notes  
 En faisant précéder une définition d'interface, l'attribut d' **objet** C\+\+ provoque l'interface à placer dans le fichier .idl en tant qu'interface personnalisée.  
  
 Les interfaces marqué avec l'objet doivent hériter d' **IUnknown**.  Cette condition est satisfaite si les interfaces de base l'une d'elles héritent d' **IUnknown**.  Si interface de base n'hérite pas d' **IUnknown**, le compilateur provoque l'interface marquée avec **objet** pour dériver d' **IUnknown**.  
  
## Exemple  
 Consultez [nonbrowsable](../windows/nonbrowsable.md) pour un exemple d'utilisation **objet**.  
  
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
 [dual](../windows/dual.md)   
 [dispinterface](../windows/dispinterface.md)   
 [custom](../windows/custom-cpp.md)   
 [\_\_interface](../cpp/interface.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)