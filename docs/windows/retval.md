---
title: "retval | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.retval"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "retval attribute"
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# retval
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique le paramètre qui accepte la valeur de retour du membre.  
  
## Syntaxe  
  
```  
  
[retval]  
  
```  
  
## Notes  
 L'attribut de **retval** C\+\+ a les mêmes fonctionnalités que l'attribut de [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL.  
  
 **retval** doit apparaître sur le dernier argument dans une déclaration de fonction.  
  
## Exemple  
 Consultez l'exemple pour [pouvant être liée](../windows/bindable.md) pour un usage d'exemple de **retval**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|paramètre d'interface, méthode d'interface|  
|**reproductible**|Non|  
|**attributs requis**|**out**|  
|**attributs valides**|**in**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)