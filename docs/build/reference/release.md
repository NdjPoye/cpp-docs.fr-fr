---
title: "/RELEASE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RELEASE (option Editbin)"
  - "définition du checksum"
  - "RELEASE (option Editbin)"
  - "-RELEASE (option Editbin)"
ms.assetid: 183422eb-6b3c-474e-9589-04a0e69dec5d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RELEASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RELEASE  
```  
  
## Notes  
 Cette option définit le checksum dans l'en\-tête d'un fichier exécutable.  
  
 Le système d'exploitation requiert le checksum pour les pilotes de périphérique.  Il est recommandé de définir le checksum pour les versions release des pilotes de périphérique afin de garantir la compatibilité avec les systèmes d'exploitation futurs.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)