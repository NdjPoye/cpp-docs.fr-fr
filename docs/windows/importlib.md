---
title: "importlib | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.importlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importlib attribute"
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# importlib
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rend disponibles les types qui ont déjà été compilés dans une autre bibliothèque de types pour la bibliothèque de types en cours de création.  
  
## Syntaxe  
  
```  
  
        [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### Paramètres  
 *tlb\_file*  
 Nom d'un fichier .tlb, entre guillemets, que vous souhaitez importer dans la bibliothèque de types du projet actuel.  
  
## Notes  
 L'attribut C\+\+ **importlib** entraîne le placement d'une instruction `importlib` dans le bloc de bibliothèque du fichier .idl généré.  L'attribut **importlib** a les mêmes fonctionnalités que l'attribut MIDL [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050).  
  
## Exemple  
 Le code suivant montre un exemple d'utilisation d'**importlib** :  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## Configuration requise  
  
### Contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|N'importe où|  
|**Renouvelable**|Non|  
|**Attributs requis**|None|  
|**Attributs non valides**|Aucun|  
  
 Pour plus d'informations, consultez [Contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)