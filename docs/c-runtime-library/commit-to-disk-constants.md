---
title: "Commit-To-Disk, constantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.constants"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "commit-to-disk (constantes)"
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Commit-To-Disk, constantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
## Syntaxe  
  
```  
  
#include <stdio.h>  
```  
  
## Notes  
 Ces constantes spécifiques à Microsoft spécifient si la mémoire tampon associée au fichier ouvert est vidée aux tampons du système d'exploitation ou sur le disque.  Le mode est inclus dans la chaîne qui spécifie le type d'accès écriture\/lecture \(**"r"**, **"w"**, **"a"**, **"r\+"**, **"w\+"**, **"a\+"**\).  
  
 Les modes validés sur disque sont les suivantes :  
  
 **c**  
 Écrit le contenu non écrit dans la mémoire tampon spécifiée sur le disque.  Cette fonctionnalité validée sur disque se produit uniquement aux appels explicites à [fflush](../c-runtime-library/reference/fflush.md) ou la fonction [\_flushall](../c-runtime-library/reference/flushall.md).  Ce mode est utile lors du traitement des données sensibles.  Par exemple, si votre programme prend fin après un appel à `fflush` ou à `_flushall`, vous pouvez vous assurer que vos données ont atteint les mémoires tampons du système d'exploitation.  Toutefois, à moins qu'un fichier ouvert avec l'option de **c**, les données peuvent ne jamais la rendre le disque si le système d'exploitation se termine également.  
  
 **n**  
 Écrit le contenu non écrit dans la mémoire tampon spécifiée pour les mémoires tampons du système d'exploitation.  Le système d'exploitation peut mettre en cache les données puis déterminer le délai optimal pour écrire sur le disque.  Dans de nombreuses conditions, ce comportement exécute le comportement du programme efficace.  Toutefois, si la rétention des données est essentielle \(par exemple les informations de transactions du magasin ou de billet de plan\) utilisez l'option de **c**.  Le mode **n** est l'option par défaut.  
  
> [!NOTE]
>  Les options de **c** et de **n** ne font pas partie de la norme ANSI pour `fopen`, mais sont des extensions Microsoft et ne doivent pas être utilisées lorsque la portabilité ANSI est souhaitée.  
  
## Utilisation de la fonctionnalité validée sur disque avec le code existant  
 Par défaut, les appels à [fflush](../c-runtime-library/reference/fflush.md) ou les fonctions de la bibliothèque d'[\_flushall](../c-runtime-library/reference/flushall.md) écrivent des données aux mémoires tampon gérées par le système d'exploitation.  Le système d'exploitation détermine l'heure optimale d'écrire réellement les données sur le disque.  La fonctionnalité validée sur disque de la bibliothèque runtime vous permet de garantir que les données critique est écrite directement sur le disque plutôt que sur les mémoires tampons du système d'exploitation.  Vous pouvez attribuer cette fonction dans un programme existant sans la réécrire pour lier les fichiers objet avec COMMODE.OBJ.  
  
 Dans le fichier exécutable résultant, les appels à `fflush` entrez le contenu de la mémoire tampon directement sur le disque, et les appels à `_flushall` entrez le contenu de tous les tampons sur le disque.  Ces deux fonctions sont les seules affectées par COMMODE.OBJ.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [E\/S de flux](../c-runtime-library/stream-i-o.md)   
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)