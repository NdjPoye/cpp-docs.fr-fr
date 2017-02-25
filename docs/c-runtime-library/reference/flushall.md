---
title: "flushall | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_flushall"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "flushall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flushall (fonction)"
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _flushall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vide tous les flux ; désactive toutes les mémoires tampons.  
  
## Syntaxe  
  
```  
int _flushall( void );  
```  
  
## Valeur de retour  
 `_flushall` renvoie le nombre de flux ouverts \(entrées et sorties\).  Aucun retour d'erreur.  
  
## Notes  
 Par défaut, la fonction `_flushall` écrit aux fichiers appropriés le contenu de toutes les mémoires tampons associées aux flux de sortie ouverts.  Toutes les mémoires tampons associées aux flux d'entrée ouverts sont vidées de leur contenu actuel. \(Ces tampons sont normalement conservées par le système d'exploitation, qui détermine l'heure optimale pour écrire les données automatiquement sur le disque : lorsqu'une mémoire tampon est complète, lorsqu'un flux est fermé, ou lorsqu'un programme se termine normalement sans fermer les flux.\)  
  
 Si une lecture suit un appel à `_flushall`, les nouvelles données sont lues à partir des fichiers d'entrée dans les mémoires tampons.  Tous les flux restent ouverts après l'appel à `_flushall`.  
  
 La fonctionnalité validée sur disque de la bibliothèque runtime vous permet de garantir que les données critique est écrite directement sur le disque plutôt que sur les mémoires tampons du système d'exploitation.  Sans réécrire un programme existant, vous pouvez activer cette fonctionnalité en liant les fichiers objets du programme avec Commode.obj.  Dans le fichier exécutable obtenu, les appels à `_flushall` lisent le contenu de toutes les mémoires tampons sur le disque.  Seuls `_flushall` et `fflush` sont affectés par Commode.obj.  
  
 Pour plus d'informations sur le contrôle de la fonctionnalité validée sur disque, consultez [Flux E\/S](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md), et [\_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_flushall`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
  **Il existait 3 flux purgés**   
## Équivalent .NET Framework  
  
-   [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
-   [System::IO::StreamWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.flush.aspx)  
  
-   [System::IO::TextWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.textwriter.flush.aspx)  
  
-   [System::IO::BinaryWriter::Flush](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.flush.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)