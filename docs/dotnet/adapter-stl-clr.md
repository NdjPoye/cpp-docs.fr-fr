---
title: "adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "<cliext/adapter>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <adapter> (STL/CLR)"
  - "en-tête <cliext/adapter> (STL/CLR)"
  - "adaptateur (STL/CLR)"
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'en\-tête `<cliext/adapter>` de STL\/CLR spécifie deux classes de modèle \(`collection_adapter` et `range_adapter`\), la fonction `make_collection`de modèle.  
  
## Syntaxe  
  
```  
#include <cliext/adapter>  
```  
  
## Notes  
  
|Classe|Description|  
|------------|-----------------|  
|[collection\_adapter](../dotnet/collection-adapter-stl-clr.md)|Encapsule la collection de \(BCL\) de la bibliothèque de classes de base comme plage.|  
|[range\_adapter](../dotnet/range-adapter-stl-clr.md)|Encapsule la plage comme une collection de BCL.|  
  
|Fonction|Description|  
|--------------|-----------------|  
|[make\_collection](../dotnet/make-collection-stl-clr.md)|Crée un adaptateur de plage à l'aide d'une paire d'itération.|  
  
## Configuration requise  
 **En\-tête :** \<cliext\/adapter\>  
  
 **Espace de noms** cliext  
  
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)