---
title: "exit, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit (fonction)"
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# exit, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fonction **exit**, déclarée dans le fichier Include standard STDLIB.H, termine un programme C\+\+.  
  
 La valeur fournie comme argument à **exit** est retournée au système d'exploitation en tant que code de retour ou code de sortie du programme.  Par convention, un code de retour égal à zéro signifie que le programme s'est terminé correctement.  
  
> [!NOTE]
>  Vous pouvez utiliser les constantes `EXIT_FAILURE` et `EXIT_SUCCESS`, définies dans STDLIB.H, pour indiquer le succès ou l'échec de votre programme.  
  
 Émettre une instruction `return` à partir de la fonction **main** équivaut à appeler la fonction **exit** avec la valeur de retour comme argument.  
  
 Pour plus d'informations, consultez [exit](../c-runtime-library/reference/exit-exit-exit.md) dans la *Référence de la bibliothèque runtime*.  
  
## Voir aussi  
 [Terminaison du programme](../cpp/program-termination.md)