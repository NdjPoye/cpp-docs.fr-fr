---
title: "Erreur du compilateur C2002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2002"
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

constante à caractères larges non valide  
  
 La constante à caractères multioctets n'est pas valide.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  La constante à caractères larges contient plus d'octets que prévu.  
  
2.  L'en\-tête standard STDDEF.h n'est pas inclus.  
  
3.  Les caractères larges ne peuvent pas être concaténés avec des littéraux de chaîne ordinaires.  
  
4.  Une constante à caractères larges doit être précédée du caractère 'L' :  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Pour Microsoft C\+\+, les arguments de texte d'une directive de préprocesseur doivent être en ASCII.  Par exemple, la directive `#pragma message(L"string")` n'est pas valide.