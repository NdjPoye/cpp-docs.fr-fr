---
title: "dispinterface | Microsoft Docs"
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
  - "vc-attr.dispinterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dispinterface (attribut)"
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dispinterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Place une interface dans le fichier .idl comme interface de dispatch.  
  
## Syntaxe  
  
```  
  
[dispinterface]  
  
```  
  
## Notes  
 Quand l’attribut C\+\+ **dispinterface** précède une interface, il fait en sorte qu’elle soit placée dans le bloc de bibliothèque dans le fichier .idl généré.  
  
 Une interface de dispatch dérivent de `IDispatch`, sauf si vous spécifiez une classe de base. Vous devez spécifier un [id](../windows/id.md) pour les membres d’une interface de dispatch.  
  
 L’exemple d’utilisation de [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) dans la documentation MIDL :  
  
```  
dispinterface helloPro   
   { interface hello; };   
```  
  
 n’est pas valide pour l’attribut **dispinterface**.  
  
## Exemple  
 Pour obtenir un exemple montrant comment utiliser **dispinterface**, consultez l’exemple de [bindable](../windows/bindable.md).  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|`interface`|  
|**Renouvelable**|Non|  
|**Attributs requis**|Aucun|  
|**Attributs non valides**|**dual**, **object**, **oleautomation**, `local`, **ms\_union**|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes by Usage](../windows/attributes-by-usage.md)   
 [uuid](../windows/uuid-cpp-attributes.md)   
 [dual](../windows/dual.md)   
 [custom](../windows/custom-cpp.md)   
 [object](../windows/object-cpp.md)   
 [\_\_interface](../cpp/interface.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)