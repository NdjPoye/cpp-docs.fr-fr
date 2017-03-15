---
title: "importidl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.importidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importidl attribute"
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# importidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Insère le fichier spécifié .idl dans le fichier généré .idl.  
  
## Syntaxe  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### Paramètres  
 `idl_file`  
 Identifie le nom du fichier .idl à fusionner avec le fichier .idl qui sera généré pour votre application.  
  
## Notes  
 L'attribut d' **importidl** C\+\+ place la section en dehors de le bloc bibliothèque \(dans `idl_file`\) dans le fichier généré .idl de votre programme et la section bibliothèque \(dans `idl_file`\) dans la section bibliothèque du fichier généré .idl de votre programme.  
  
 Vous pouvez utiliser **importidl**, par exemple, si vous souhaitez utiliser un fichier main\-codé .idl à votre fichier généré .idl.  
  
## Exemple  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)