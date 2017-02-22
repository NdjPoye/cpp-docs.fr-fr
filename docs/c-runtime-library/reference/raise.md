---
title: "raise | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "raise"
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
  - "Raise"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "programmes (C++), envoyer des signaux à des programmes en cours d'exécution"
  - "raise (fonction)"
  - "signaux"
  - "signaux, envoyer à des programmes en cours d'exécution"
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# raise
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Envoie un signal au programme en cours de exécution.  
  
> [!NOTE]
>  N'utilisez pas cette méthode pour arrêter une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], sauf dans les scénarios de test ou de débogage.  Les méthodes de programmation ou de l'interface utilisateur pour fermer une application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ne sont pas autorisées d'après la section 3.6 des [critères de certification pour les applications Windows 8](http://go.microsoft.com/fwlink/?LinkId=262889).  Pour plus d'informations, consultez [Cycle de vie d'une application \(applications du Windows Store\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntaxe  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### Paramètres  
 *sig*  
 Signal pour être déclenché.  
  
## Valeur de retour  
 En cas de succès, **raise** retourne 0.  Sinon, il retourne une valeur différente de zéro.  
  
## Notes  
 La fonction **déclencher** envoie *sig* au programme d'exécution.  Si un appel précédent à **signal** a installé une fonction de gestion de signal pour *sig*, **déclencher** exécute cette fonction.  Si aucune fonction gestionnaire n'a été installée, l'action par défaut associée avec la valeur de signal *sig* est prise, comme suit.  
  
|signal|Signification|Par défaut|  
|------------|-------------------|----------------|  
|`SIGABRT`|Fin anormale|Termine le programme appelant par le code de sortie 3|  
|`SIGFPE`|Erreur de virgule flottante|Termine le programme appelant|  
|`SIGILL`|instruction non conforme|Termine le programme appelant|  
|`SIGINT`|CTRL\+C Interrompre|Termine le programme appelant|  
|`SIGSEGV`|Accès au stockage non conforme|Termine le programme appelant|  
|`SIGTERM`|Demande d'arrêt envoyée au programme|Ignore le signal|  
  
 Si l'argument n'est pas un signal valide comme spécifié ci\-dessus, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si non gérée, cette fonction affecte `errno` à `EINVAL` et retourne une valeur différente de zéro.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**raise**|\<signal.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)