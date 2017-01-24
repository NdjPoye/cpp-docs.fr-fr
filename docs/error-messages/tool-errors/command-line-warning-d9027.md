---
title: "Avertissement de ligne de commande D9027 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9027"
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement de ligne de commande D9027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier source '\<nomfichier\>' ignoré  
  
 CL.exe a ignoré le fichier source en entrée.  
  
 Cet avertissement peut être provoqué par un espace entre l'option \/Fo et un nom de fichier de sortie sur une ligne de commande ayant l'option \/c.  Par exemple :  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Comme il y a un espace entre \/Fo et `output.obj,` CL.exe considère que `output.obj` est le nom du fichier d'entrée.  Pour résoudre le problème, supprimez l'espace :  
  
```  
cl /c /Fooutput.obj input.c   
```