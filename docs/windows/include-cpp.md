---
title: "include (C++) | Microsoft Docs"
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
  - "vc-attr.include"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include attribute"
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# include (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie un ou plusieurs fichiers d'en\-tête à inclure dans le fichier généré .idl.  
  
## Syntaxe  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### Paramètres  
 *header\_file*  
 Le nom d'un fichier que vous souhaitez inclus dans le fichier généré .idl.  
  
## Notes  
 L'attribut d' **incluez** C\+\+ provoque une instruction d' `#include` à placer sous l'instruction d' `import "docobj.idl"` dans le fichier généré .idl.  
  
 L'attribut d' **incluez** C\+\+ a les mêmes fonctionnalités que l'attribut d' [incluez](http://msdn.microsoft.com/library/windows/desktop/aa367052) MIDL.  
  
## Exemple  
 Le code suivant indique comment utiliser **incluez**.  Pour cet exemple, le fichier include.h contient une seule instruction \#include.  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|n'importe où|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)