---
title: "v1_enum | Microsoft Docs"
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
  - "vc-attr.v1_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "v1_enum attribute"
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# v1_enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Règles que le type énuméré spécifié soit transmis comme une entité 32 bits plutôt que la valeur par défaut 16 bits.  
  
## Syntaxe  
  
```  
  
[v1_enum]  
  
```  
  
## Notes  
 L'attribut de **v1\_enum** C\+\+ a les mêmes fonctionnalités que l'attribut de [v1\_enum](http://msdn.microsoft.com/library/windows/desktop/aa367303) MIDL.  
  
## Exemple  
 Le code suivant illustre une utilisation de **v1\_enum**:  
  
```  
// cpp_attr_ref_v1_enum.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export, v1_enum]   
enum eList {   
   e1 = 1,   
   e2 = 2  
};  
```  
  
## Configuration requise  
  
### contexte d'attribut  
  
|||  
|-|-|  
|**S'applique à**|type énuméré|  
|**reproductible**|Non|  
|**attributs requis**|Aucun|  
|**attributs valides**|Aucun|  
  
 Pour plus d'informations sur les contextes d'attribut, consultez [contextes d'attribut](../windows/attribute-contexts.md).  
  
## Voir aussi  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/fr-fr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)