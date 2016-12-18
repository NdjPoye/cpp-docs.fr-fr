---
title: "inattendu (CRT) | Microsoft Docs"
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
  - "unexpected"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "unexpected"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fonction inattendue"
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# inattendu (CRT)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle `terminate` ou une fonction que vous spécifiez en utilisant `set_unexpected`.  
  
## Syntaxe  
  
```  
void unexpected( void );  
```  
  
## Notes  
 La routine `unexpected` n'est pas utilisée avec l'implémentation actuelle de la gestion des exceptions C\+\+.  Par défaut, `unexpected` appelle `terminate`.  Vous pouvez modifier ce comportement par défaut en écrivant une fonction d'arrêt personnalisée et en appelant `set_unexpected` avec le nom de votre fonction comme son argument.  La routine `unexpected`appelle toujours la dernière fonction donnée comme argument à `set_unexpected`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`unexpected`|\<EH.H\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 [System::Exception Class.](https://msdn.microsoft.com/en-us/library/system.exception.aspx)  
  
## Voir aussi  
 [Routines de la gestion d'exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [\_set\_se\_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set\_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set\_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)