---
title: "Erreur d&#39;ex&#233;cution C R6002 | Microsoft Docs"
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
  - "R6002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6002"
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
caps.latest.revision: 10
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur d&#39;ex&#233;cution C R6002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

prise en charge de la virgule flottante non chargée  
  
 La bibliothèque à virgule flottante nécessaire n'était pas liée.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Le programme a été compilé ou lié avec une option, telle que \/FPi87, qui exige un coprocesseur alors qu'il était exécuté sur un ordinateur sans coprocesseur.  
  
2.  Une chaîne de format destinée à une fonction `printf_s` ou `scanf_s` contenait une spécification de format à virgule flottante alors que le programme ne contenait ni variables ni valeurs à virgule flottante.  
  
3.  Le compilateur réduit la taille d'un programme en chargeant le support à virgule flottante uniquement quand c'est nécessaire.  Dans la mesure où il ne peut pas détecter de spécifications de format à virgule flottante dans les chaînes de format, le compilateur ne charge pas les routines à virgule flottant nécessaires.  
  
4.  Utilisez un argument à virgule flottante pour établir une correspondance avec la spécification de format à virgule flottante, ou procédez à une assignation à virgule flottante ailleurs dans le programme.  Le support à virgule flottante est ainsi chargé.  
  
5.  Dans un programme à plusieurs langages, une bibliothèque C a été spécifiée avant une bibliothèque FORTRAN au moment de la liaison du programme.  Reliez et spécifiez la bibliothèque C en dernier.