---
title: "ArrayReference::operator=, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 131a4612-d66b-48e4-90af-c665ccc0cce4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator=, op&#233;rateur
Assigne l'objet spécifié à l'objet [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) actif à l'aide de la sémantique de déplacement.  
  
## Syntaxe  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& __otherArg);  
  
```  
  
#### Paramètres  
 `__ otherArg`  
 Objet déplacé vers l'objet `ArrayReference` actif.  
  
## Valeur de retour  
 Référence à un objet de type `ArrayReference`.  
  
## Notes  
 `Platform::ArrayReference` est un modèle de classe C\+\+ standard, et non une classe de référence.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::ArrayReference \(classe\)](../cppcx/platform-arrayreference-class.md)