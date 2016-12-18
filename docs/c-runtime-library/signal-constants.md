---
title: "signal, constantes | Microsoft Docs"
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
  - "SIGTERM"
  - "SIGFPE"
  - "SIGABRT"
  - "SIGILL"
  - "SIGINT"
  - "SIGSEGV"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIGABRT (constante)"
  - "SIGFPE (constante)"
  - "SIGILL (constante)"
  - "SIGINT (constante)"
  - "signal (constantes)"
  - "SIGSEGV (constante)"
  - "SIGTERM (constante)"
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# signal, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
#include <signal.h>  
```  
  
## Notes  
 L'argument `sig` doit être l'une des constantes manifestes répertoriées ci\-dessous \(défini dans SIGNAL.H\).  
  
 `SIGABRT`  
 Terminaison anormale  L'action par défaut met fin au programme appelant avec le code de sortie 3.  
  
 `SIGABRT_COMPAT`  
 Identique à SIGABRT.  Pour la compatibilité avec d'autres plateformes.  
  
 `SIGFPE`  
 Erreur à virgule flottante, telle que le dépassement de capacité, la division par zéro, ou l'opération non valide.  L'action par défaut met fin au programme appelant.  
  
 `SIGILL`  
 instruction non conforme.  L'action par défaut met fin au programme appelant.  
  
 `SIGINT`  
 CTRL\+C Interrompt.  L'action par défaut met fin au programme appelant avec le code de sortie 3.  
  
 `SIGSEGV`  
 Accès au stockage non conforme.  L'action par défaut met fin au programme appelant.  
  
 `SIGTERM`  
 Demande d'arrêt envoyée au programme.  L'action par défaut met fin au programme appelant avec le code de sortie 3.  
  
 `SIG_ERR`  
 Un type de retour d'un signal indiquant qu'une erreur s'est produite.  
  
## Voir aussi  
 [signal](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)