---
title: "helpcontext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpcontext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpcontext attribute"
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# helpcontext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie un ID de contexte qui laisse les informations de voir sur cet élément dans le fichier d'aide.  
  
## Syntaxe  
  
```  
  
      [ helpcontext(  
   id  
) ]  
```  
  
#### Paramètres  
 `id`  
 l'ID de contexte de la rubrique d'aide.  Consultez [Aide HTML : aide contextuelle pour vos programmes](../mfc/html-help-context-sensitive-help-for-your-programs.md) pour plus d'informations sur les identificateurs de contexte.  
  
## Notes  
 L'attribut de **helpcontext** C\+\+ a les mêmes fonctionnalités que l'attribut de [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL.  
  
## Exemple  
 Consultez l'exemple pour [defaultvalue](../windows/defaultvalue.md) pour un exemple d'utilisation **helpcontext**.  
  
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
 [helpstring](../windows/helpstring.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)