---
title: "includelib (C++) | Microsoft Docs"
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
  - "vc-attr.includelib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includelib attribute"
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# includelib (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère un fichier .idl ou .h à inclure dans le fichier généré .idl.  
  
## Syntaxe  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### Paramètres  
 *name.idl*  
 Le nom du fichier .idl que vous souhaitez inclus dans le fichier généré .idl.  
  
## Notes  
 L'attribut d' `includelib` C\+\+ génère un fichier .idl ou .h à inclure dans le fichier généré .idl, après l'instruction d' `importlib` .  
  
## Exemple  
 Le code suivant est affiché dans un fichier .cpp :  
  
```  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|n'importe où|  
|**reproductible**|Oui|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [include](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)