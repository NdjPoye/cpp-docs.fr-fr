---
title: "custom (C++) | Microsoft Docs"
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
  - "vc-attr.custom"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom attributes, defining"
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# custom (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les métadonnées pour un objet dans la bibliothèque de types.  
  
## Syntaxe  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### Paramètres  
 *uuid*  
 ID unique.  
  
 *correspondante*  
 Une valeur qui peut être mise dans un variant.  
  
## Notes  
 L'attribut de **personnalisée** C\+\+ provoquera des informations à placer dans la bibliothèque de types.  Vous aurez besoin d'un outil qui indique la valeur personnalisée de la bibliothèque de types.  
  
 L'attribut de **personnalisée** a les mêmes fonctionnalités que l'attribut de [personnalisée](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|COM `interface`, **classe**, `enum`s, méthodes d' `idl_module` , membres d'interface, paramètres d'interface, `typedef`s, **union**s, `struct`s|  
|**reproductible**|Oui|  
|**attributs requis**|**coclasse** \(en cas de utilisation de la classe\)|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)