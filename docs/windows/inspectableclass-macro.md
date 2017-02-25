---
title: "InspectableClass, macro | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::InspectableClass"
dev_langs: 
  - "C++"
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# InspectableClass, macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit le nom et le niveau de confiance de la classe d'exécution.  
  
## Syntaxe  
  
```cpp  
  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
  
```  
  
#### Paramètres  
 `runtimeClassName`  
 Le nom textuel complet de la classe d'exécution.  
  
 `trustLevel`  
 Une des valeurs énumérées [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx).  
  
## Notes  
 La macro `InspectableClass` peut être utilisée uniquement avec des types [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Configuration requise  
 **En\-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## Voir aussi  
 [RuntimeClass, classe](../windows/runtimeclass-class.md)