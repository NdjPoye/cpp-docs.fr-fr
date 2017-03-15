---
title: "version (C++) | Microsoft Docs"
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
  - "vc-attr.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version attribute"
  - "version information, version attribute"
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# version (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Identifie une version particulière entre plusieurs versions d'une classe.  
  
## Syntaxe  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### Paramètres  
 *version*  
 Numéro de la coclasse.  Si elle n'est pas spécifiée, 1,0 se trouvent dans le fichier .idl.  
  
## Notes  
 L'attribut de **version** C\+\+ a les mêmes fonctionnalités que l'attribut de [version](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL et est passé au fichier généré .idl.  
  
## Exemple  
 Consultez l'exemple de [pouvant être liée](../windows/bindable.md) pour un usage d'exemple de **version**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**classe**, `struct`|  
|**reproductible**|Non|  
|**attributs requis**|**coclasse**|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)