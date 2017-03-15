---
title: "/SWAPRUN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/swaprun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN (option Editbin)"
  - "SWAPRUN (option Editbin)"
  - "-SWAPRUN (option Editbin)"
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /SWAPRUN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{[!]NET|[!]CD}  
```  
  
## Notes  
 Cette option modifie l'image pour indiquer au système d'exploitation de copier l'image vers un fichier d'échange et de l'exécuter à partir de là.  Utilisez cette option pour les images qui résident sur des réseaux ou sur un média amovible.  
  
 Vous pouvez ajouter ou supprimer les qualificateurs NET ou CD :  
  
-   NET indique que l'image réside sur un réseau.  
  
-   CD indique que l'image réside sur un CD\-ROM ou un support amovible similaire.  
  
-   Utilisez \!NET et \!CD pour inverser l'effet de NET et CD.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)