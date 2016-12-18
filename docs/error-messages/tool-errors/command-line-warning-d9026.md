---
title: "Avertissement de ligne de commande D9026 | Microsoft Docs"
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
  - "D9026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9026"
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement de ligne de commande D9026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les options s'appliquent à toute la ligne de commande  
  
 Une option a été spécifiée dans une commande après un nom de fichier.  L'option a été appliquée au fichier précédent.  
  
 Par exemple, dans la commande  
  
```  
CL verdi.c /G5 puccini.c  
```  
  
 c'est le fichier VERDI.c qui est compilé à l'aide de l'option \/G5, pas par l'option \/G4 par défaut.  
  
 Ce comportement est différent de celui des versions précédentes, qui n'appliquaient que les options spécifiées avant le nom de fichier, ce qui entraînait la compilation de VERDI.c par \/G4 et de PUCCINI.c par \/G5.