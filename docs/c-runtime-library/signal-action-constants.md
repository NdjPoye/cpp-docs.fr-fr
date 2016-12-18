---
title: "signal, constantes action | Microsoft Docs"
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
  - "SIG_IGN"
  - "SIG_DFL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIG_DFL (constante)"
  - "SIG_IGN (constante)"
  - "signal (constantes action)"
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# signal, constantes action
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'action entreprise lorsque le signal d'interruption est reçu dépend de la valeur de`func`.  
  
## Syntaxe  
  
```  
#include <signal.h>  
```  
  
## Notes  
 L'argument `func` doit être soit une adresse de fonction soit l'une des constantes manifestes répertoriées ci\-dessous et définies dans SIGNAL.H.  
  
 `SIG_DFL`  
 Utilises la réponse du système par défaut.  Si le programmes appelant utilise des flux I\/O, les mémoires tampons créés par la bibliothèque d'exécutables ne sont pas vidées.  
  
 `SIG_IGN`  
 Ignore le signal d'interruption.  Cette valeur ne doit jamais être fournie pour `SIGFPE`, étant donné que l'état à virgule flottante du processus n'est pas défini.  
  
 `SIG_SGE`  
 Indique qu'une erreur s'est produite dans le signal.  
  
 `SIG_ACK`  
 Indique qu'un accusé de réception a été reçu.  
  
 `SIG_ERR`  
 Un type de retour d'un signal indiquant qu'une erreur s'est produite.  
  
## Voir aussi  
 [signal](../c-runtime-library/reference/signal.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)