---
title: "auto_gcroot, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_gcroot"
  - "msclr.auto_gcroot"
  - "auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot"
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_gcroot, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La gestion de ressources automatique \(comme [auto\_ptr, classe](../standard-library/auto-ptr-class.md)\) qui peut être utilisée pour intégrer une poignée virtuelle dans un type natif.  
  
## Syntaxe  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### Paramètres  
 `_element_type`  
 Le type géré à intégré.  
  
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_gcroot.h\>  
  
 **Espace de nom** msclr  
  
## Voir aussi  
 [auto\_gcroot](../dotnet/auto-gcroot.md)   
 [auto\_gcroot, membres](../dotnet/auto-gcroot-members.md)   
 [Comment : déclarer des handles dans les types natifs](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto\_handle, classe](../dotnet/auto-handle-class.md)