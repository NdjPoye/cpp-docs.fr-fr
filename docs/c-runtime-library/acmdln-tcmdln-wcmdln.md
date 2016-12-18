---
title: "_acmdln, _tcmdln, _wcmdln | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcmdln"
  - "_acmdln"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_acmdln"
  - "acmdln"
  - "_wcmdln"
  - "wcmdln"
  - "_tcmdln"
  - "tcmdln"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_acmdln (variable globale)"
  - "_tcmdln (variable globale)"
  - "_wcmdln (variable globale)"
  - "acmdln (variable globale)"
  - "tcmdln (variable globale)"
  - "wcmdln (variable globale)"
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _acmdln, _tcmdln, _wcmdln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Variable globale CRT interne.  Ligne de commande.  
  
## Syntaxe  
  
```  
char * _acmdln; wchar_t * _wcmdln;  #ifdef WPRFLAG    #define _tcmdln _wcmdln #else    #define _tcmdln _acmdln  
```  
  
## Notes  
 Ces variables internes CRT stockent la ligne de commande entière.  Si elles sont exposées dans les symboles exportées pour le CRT, elles ne sont pas destinées pour autant à être utilisées dans votre code.  `_acmdln` stocke les données sous forme de chaîne de caractères.  `_wcmdln` stocke les données sous forme de chaîne de caractères larges.  `_tcmdln` peut être défini comme `_acmdln` ou  `_wcmdln`, selon le cas.  
  
## Voir aussi  
 [Variables globales](../c-runtime-library/global-variables.md)