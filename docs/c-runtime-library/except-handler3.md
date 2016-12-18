---
title: "_except_handler3 | Microsoft Docs"
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
  - "_except_handler3"
apilocation: 
  - "msvcrt.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_except_handler3"
  - "except_handler3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_except_handler3 (fonction)"
  - "except_handler3 (fonction)"
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _except_handler3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonction CRT interne.  Utilisée par une infrastructure pour rechercher le gestionnaire d'exceptions approprié pour traiter l'exception actuelle.  
  
## Syntaxe  
  
```  
int _except_handler3(    PEXCEPTION_RECORD exception_record,    PEXCEPTION_REGISTRATION registration,    PCONTEXT context,    PEXCEPTION_REGISTRATION dispatcher );  
```  
  
#### Paramètres  
 \[in\] `exception_record`  
 Informations sur l'exception spécifique.  
  
 \[in\] `registration`  
 Enregistrement qui indique la table d'étendue qui doit être utilisée pour rechercher le gestionnaire d'exceptions.  
  
 \[in\] `context`  
 Réservé.  
  
 \[in\] `dispatcher`  
 Réservé.  
  
## Valeur de retour  
 Si une exception doit être écartée, retourne `DISPOSITION_DISMISS`.  Si l'exception doit être montée d'un niveau aux gestionnaires d'exceptions d'encapsulation, retourne `DISPOSITION_CONTINUE_SEARCH`.  
  
## Notes  
 Si cette méthode trouve un gestionnaire d'exceptions approprié, l'exception est passée au gestionnaire.  Dans ce cas, cette méthode ne retourne pas au code qui l'a appelée et la valeur de retour est inutile.  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)