---
title: "helpstring | Microsoft Docs"
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
  - "vc-attr.helpstring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstring attribute [C++]"
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# helpstring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie une chaîne de caractères utilisée pour décrire l'élément auquel elle s'applique.  
  
## Syntaxe  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### Paramètres  
 `string`  
 le texte de la chaîne d'aide.  
  
## Notes  
 L'attribut de **helpstring** C\+\+ a les mêmes fonctionnalités que l'attribut de [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [defaultvalue](../windows/defaultvalue.md) pour un exemple d'utilisation **helpstring**.  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`, `typedef`, **classe**, méthode, propriété|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpfile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)