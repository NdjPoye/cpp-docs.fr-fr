---
title: "Exceptions (C/C++) | Microsoft Docs"
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
  - "ERROR_MOD_NOT_FOUND"
  - "vcppException"
  - "ERROR_SEVERITY_ERROR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion d'exceptions C++, chargement différé de DLL"
  - "chargement différé de DLL, exceptions"
  - "exception ERROR_MOD_NOT_FOUND"
  - "exception ERROR_SEVERITY_ERROR"
  - "vcppException"
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exceptions (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deux codes d'exception peuvent être obtenus en cas de défaillance :  
  
-   pour une défaillance **LoadLibrary** ;  
  
-   pour une défaillance **GetProcAddress**.  
  
 Voici les informations sur les exceptions :  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Les codes d'exception générés sont les valeurs standard VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_MOD\_NOT\_FOUND\) et VcppException\(ERROR\_SEVERITY\_ERROR, ERROR\_PROC\_NOT\_FOUND\).  L'exception passe un pointeur à une structure **DelayLoadInfo** dans la valeur qui peut être récupérée par **GetExceptionInformation** dans la structure [EXCEPTION\_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082), champ ExceptionInformation\[0\].  
  
 En outre, si les bits incorrects sont définis dans le champ grAttrs, l'exception ERROR\_INVALID\_PARAMETER est générée.  Cette exception est irrécupérable dans tous les cas.  
  
 Pour plus d'informations, consultez [Définitions des structures et constantes](../../build/reference/structure-and-constant-definitions.md).  
  
## Voir aussi  
 [Gestion et notification des erreurs](../../build/reference/error-handling-and-notification.md)