---
title: "Expressions utilis&#233;es dans le pr&#233;traitement d&#39;un makefile | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "expressions (C++), prétraitement d'un makefile"
  - "makefiles, prétraiter"
  - "prétraitement des makefiles"
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Expressions utilis&#233;es dans le pr&#233;traitement d&#39;un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La directive **\!IF** ou **\!ELSE IF** `constantexpression` est composée de constantes entières \(notation décimale ou en langage C\), de constantes de chaîne ou de commandes.  Utilisez les parenthèses pour regrouper les expressions.  Les expressions utilisent une arithmétique de type entier long signé comme celle du langage C ; les nombres ont un format complément à 2 32 bits dans la plage – 2147483648 à 2147483647.  
  
 Les expressions peuvent utiliser des opérateurs qui agissent sur les valeurs des constantes, les codes de sortie des commandes, les chaînes, les macros et les chemins d'accès des systèmes de fichiers.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Opérateurs de prétraitement d'un makefile](../build/makefile-preprocessing-operators.md)  
  
 [Exécution d'un programme en prétraitement](../build/executing-a-program-in-preprocessing.md)  
  
## Voir aussi  
 [Prétraitement d'un makefile](../build/makefile-preprocessing.md)