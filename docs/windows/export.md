---
title: "export | Microsoft Docs"
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
  - "vc-attr.export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "export attribute"
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# export
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Provoque une structure de données soient placées dans le fichier .idl.  
  
## Syntaxe  
  
```  
  
[export]  
  
```  
  
## Notes  
 L'attribut d' **exportation** C\+\+ provoque une structure de données soient placées dans le fichier .idl puis à être disponible dans la bibliothèque de types dans un format binaire\-compatible qui le rend disponible avec n'importe quel langage.  
  
 Vous ne pouvez pas appliquer l'attribut d' **exportation** à une classe même si la classe possède les membres publics \(l'équivalent d' `struct`\).  
  
 Si vous exportez `enum`sans nom s ou `struct`s, ils seront des noms fournis qui commencent par **\_\_unnamed***X*, où *x* est un numéro séquentiel.  
  
 Les définitions de types valides pour l'exportation sont les types de base, des structures, des unions, les enums, ou les identificateurs de type.  Consultez [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) pour plus d'informations.  
  
## Exemple  
 Le code suivant montre comment utiliser l'attribut d' **exportation** :  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|**union**, `typedef`, `enum`, `struct`, ou `interface`|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)