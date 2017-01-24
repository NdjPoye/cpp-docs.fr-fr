---
title: "stdin, stdout, stderr | Microsoft Docs"
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
  - "stdin"
  - "stderr"
  - "stdout"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "flux d'erreur standard"
  - "flux d'entrée standard"
  - "flux de sortie standard"
  - "stderr (fonction)"
  - "stdin (fonction)"
  - "stdout (fonction)"
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# stdin, stdout, stderr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## Notes  
 Il s'agit des flux de données standard pour l'entrée, la sortie et la sortie d'erreur.  
  
 Par défaut, l'entrée standard est lue à partir du clavier, tandis que la sortie standard et l'erreur standard sont imprimées à l'écran.  
  
 Les pointeurs de flux suivants sont disponibles pour accéder aux sources de données standard :  
  
|Pointeur|Stream|  
|--------------|------------|  
|`stdin`|entrée standard|  
|**stdout**|sortie standard|  
|`stderr`|Erreur standard|  
  
 Ces pointeurs peuvent être utilisés comme arguments des fonctions.  Certaines fonctions, telles que **getchar** et `putchar`, utilisez `stdin` et **stdout** automatiquement.  
  
 Ces pointeurs sont des constantes, et ne peuvent pas être affectés à de nouvelles valeurs.  La fonction `freopen` permet de rediriger les flux de données dans les fichiers disque ou d'autres périphériques.  Le système d'exploitation vous permet de rediriger la sortie standard d'un programme et la sotie au niveau de commande.  
  
## Voir aussi  
 [E\/S de flux](../c-runtime-library/stream-i-o.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)