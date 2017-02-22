---
title: "propput | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.propput"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "propput attribute"
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# propput
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie une fonction de définition de propriété.  
  
## Syntaxe  
  
```  
  
[propput]  
  
```  
  
## Notes  
 L'attribut C\+\+ **propput** a les mêmes fonctionnalités que l'attribut MIDL [propput](http://msdn.microsoft.com/library/windows/desktop/aa367146).  
  
## Exemple  
 Consultez l'exemple pour [bindable](../windows/bindable.md) pour obtenir un exemple d'utilisation de **propput**.  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|Méthode|  
|**Renouvelable**|Non|  
|**Attributs requis**|None|  
|**Attributs non valides**|**propget**, **propputref**|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propputref](../windows/propputref.md)