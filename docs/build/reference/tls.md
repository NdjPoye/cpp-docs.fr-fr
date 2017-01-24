---
title: "/TLS | Microsoft Docs"
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
  - "/TLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TLS (option Dumpbin)"
  - "-TLS (option Dumpbin)"
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Affiche la structure IMAGE\_TLS\_DIRECTORY à partir d'un fichier exécutable.  
  
## Notes  
 \/TLS affiche les champs de la structure TLS ainsi que les adresses des fonctions de rappel TLS.  
  
 Si un programme n'utilise pas le stockage local des threads, son image ne contient pas de structure TLS.  Pour plus d'informations, consultez [thread](../../cpp/thread.md).  
  
 IMAGE\_TLS\_DIRECTORY est défini dans winnt.h.  
  
## Voir aussi  
 [Options DUMPBIN](../../build/reference/dumpbin-options.md)