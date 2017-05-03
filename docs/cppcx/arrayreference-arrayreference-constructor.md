---
title: "ArrayReference::ArrayReference, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::ArrayReference"
dev_langs: 
  - "C++"
ms.assetid: 9fc7dfcf-47af-40ba-a697-da476fb90efc
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::ArrayReference, constructeur
Initialise une nouvelle instance de la classe [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md).  
  
## Syntaxe  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
#### Paramètres  
 `dataArg`  
 Pointeur vers les données de tableau.  
  
 `sizeArg`  
 Nombre d'éléments du tableau source.  
  
 `otherArg`  
 Objet `ArrayReference` dont les données sont déplacées pour initialiser la nouvelle instance.  
  
## Notes  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::ArrayReference \(classe\)](../cppcx/platform-arrayreference-class.md)   
 [Array et WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)