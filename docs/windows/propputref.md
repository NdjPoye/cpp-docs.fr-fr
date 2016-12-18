---
title: "propputref | Microsoft Docs"
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
  - "vc-attr.propputref"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propputref attribute"
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# propputref
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie une fonction de paramètre de propriété qui utilise une référence plutôt qu'une valeur.  
  
## Syntaxe  
  
```  
  
[propputref]  
  
```  
  
## Notes  
 L'attribut de **propputref** C\+\+ a les mêmes fonctionnalités que l'attribut de [propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [pouvant être liée](../windows/bindable.md) pour un usage d'exemple de **propputref**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Méthode|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|**propget**, **propput**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propput](../windows/propput.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)