---
title: "_amsg_exit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_amsg_exit"
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
  - "_amsg_exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_amsg_exit"
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# _amsg_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Émet un message d'erreur d'exécution spécifié et termine votre application avec le code d'erreur 255.  
  
## Syntaxe  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
  
```  
  
#### Paramètres  
 `rterrnum`  
 Numéro d'identification d'un message d'erreur d'exécution défini par le système.  
  
## Notes  
 Cette fonction émet un message d'erreur d'exécution à **stderr** pour les applications console, ou affiche le message dans un message pour les applications Windows.  En mode débogage, vous pouvez choisir d'appeler le débogueur avant de quitter.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|\_amsg\_exit|internal.h|