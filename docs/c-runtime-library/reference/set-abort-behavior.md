---
title: "_set_abort_behavior | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_abort_behavior"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_abort_behavior"
  - "set_abort_behavior"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_set_abort_behavior (fonction)"
  - "abandonner des programmes"
  - "set_abort_behavior (fonction)"
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _set_abort_behavior
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie l'action à effectuer lorsqu'un programme est arrêté anormalement.  
  
> [!NOTE]
>  N'utilisez pas la fonction `abort` pour arrêter une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], sauf dans les scénarios de test ou de débogage.  Les méthodes de programmation ou de l'interface utilisateur pour fermer une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ne sont pas autorisées selon les [Critères de certification pour les applications Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Pour plus d'informations, consultez [Cycle de vie d'une application \(applications du Windows Store\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntaxe  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### Paramètres  
 \[in\] `flags`  
 Nouvelle valeur des indicateurs `abort`.  
  
 \[in\] `mask`  
 Masque pour les bits d'indicateurs `abort` à définir.  
  
## Valeur de retour  
 Ancienne valeur des indicateurs.  
  
## Notes  
 Il existe deux indicateurs `abort` : `_WRITE_ABORT_MSG` et `_CALL_REPORTFAULT`.  `_WRITE_ABORT_MSG` détermine si un message informatif est imprimé en cas d'arrêt anormal d'un programme.  Le message indique que l'application a appelé la fonction `abort`.  Le comportement par défaut consiste à imprimer le message.  `_CALL_REPORTFAULT`, s'il est défini, spécifie qu'un vidage sur incident de Watson est généré et signalé lorsque `abort` est appelé.  Par défaut, la création de rapport de vidage sur incident est activée dans les builds non débogage.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_set_abort_behavior`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```c  
// crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
  **Suppression du message d'abandon.  En cas de réussite, ce message est la seule sortie.**    
## Voir aussi  
 [abort](../../c-runtime-library/reference/abort.md)