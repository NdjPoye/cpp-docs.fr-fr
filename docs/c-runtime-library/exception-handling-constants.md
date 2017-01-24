---
title: "Constantes de gestion des exceptions | Microsoft Docs"
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
  - "EXCEPTION_CONTINUE_SEARCH"
  - "c.constants"
  - "EXCEPTION_CONTINUE_EXECUTION"
  - "EXCEPTION_EXECUTE_HANDLER"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "EH (constantes)"
  - "gestion des exceptions, constantes"
  - "EXCEPTION_CONTINUE_EXECUTION (constante)"
  - "EXCEPTION_CONTINUE_SEARCH (constante)"
  - "EXCEPTION_EXECUTE_HANDLER (constante)"
ms.assetid: e1870f41-be9e-46a3-a2ea-830dfbaa18fb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes de gestion des exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`EXCEPTION_CONTINUE_SEARCH`fixe, `EXCEPTION_CONTINUE_EXECUTION`, ou `EXCEPTION_EXECUTE_HANDLER` est retourné lorsqu'une exception se produit pendant l'exécution de la section protégée d'une instruction **try\-except**.  La valeur de retour détermine comment l'exception est gérée.  Pour plus d'informations, consultez [Gestion des exceptions](../cpp/try-except-statement.md) dans le *Guide de référence du langage C\+\+*.  
  
## Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)