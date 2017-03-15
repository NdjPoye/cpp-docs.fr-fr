---
title: "_cexit, _c_exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_c_exit"
  - "_cexit"
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
  - "_cexit"
  - "c_exit"
  - "_c_exit"
  - "cexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_c_exit (fonction)"
  - "_cexit (fonction)"
  - "c_exit (fonction)"
  - "cexit (fonction)"
  - "opérations de nettoyage pendant les processus"
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _cexit, _c_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exécute les opérations de nettoyage et retourne le résultat sans terminer le processus.  
  
## Syntaxe  
  
```  
void _cexit( void );  
void _c_exit( void );  
```  
  
## Notes  
 La fonction `_cexit`appelle, dans l'ordre dernier entré, premier sorti \(LIFO\), les fonctions enregistrés par `atexit` et `_onexit`.  Ensuite `_cexit` vide tous les tampons I\/O et ferme letous les flux de données ouverts avant de retourner la valeur.  `_c_exit` est le même que `_exit` mais retourne le processus appelant sans traiter `atexit` ou `_onexit` ou vider les mémoires tampon de flux.  Le comportement de `exit`,`_exit`, `_cexit`, et `_c_exit` est montré dans la table suivante.  
  
|Fonction|Comportement|  
|--------------|------------------|  
|`exit`|Effectue des procédures d'arrêt complètes de la bibliothèque C, met fin au processus, et se ferme avec le code d'état fourni.|  
|`_exit`|Effectue des procédures d'arrêt rapides de la bibliothèque C, met fin au processus, et se ferme avec le code d'état fourni.|  
|`_cexit`|Effectue des procédures d'arrêt complètes de la bibliothèque C et retourne vers son appelant, mais n'arrête pas le processus.|  
|`_c_exit`|Effectue des procédures d'arrêt rapides de bibliothèque C et retourne vers son appelant, mais n'arrête pas le processus.|  
  
 Lorsque vous appelez la fonction `_cexit` ou la fonction `_c_exit`, les destructeurs pour tout objet temporaire ou automatique, qui existent au moment de l'appel ne sont pas appelés.  Un objet automatique est un objet, qui est défini au sein d'une fonction dans laquelle l'objet n'est pas déclaré de manière statique.  Un objet temporaire est un objet créé par le compilateur.  Pour détruire un objet automatique avant d'appeler `_cexit` ou `_c_exit`, il faut explicitement appeler le destructeur de l'objet, comme suit :  
  
```  
myObject.myClass::~myClass( );  
```  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_cexit`|\<process.h\>|  
|`_c_exit`|\<process.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Équivalent .NET Framework  
 [Classe System::Diagnostics::Process](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.closemainwindow.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [\_exec, \_wexec, fonctions](../../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_spawn, \_wspawn, fonctions](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)