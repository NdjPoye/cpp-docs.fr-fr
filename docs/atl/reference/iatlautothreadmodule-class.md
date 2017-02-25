---
title: "IAtlAutoThreadModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAtlAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlAutoThreadModule class"
ms.assetid: fcb58cf9-a427-4be9-89eb-04e1ab5cc3a1
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# IAtlAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente une interface à une méthode d' `CreateInstance` .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
__interface IAtlAutoThreadModule  
  
```  
  
## Notes  
 La classe [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) dérive d' `IAtlAutoThreadModule`, son utilisation pour fournir le code pour créer un objet et récupérer un pointeur d'interface.  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)