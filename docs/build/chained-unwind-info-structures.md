---
title: "Structures d&#39;informations de d&#233;roulement cha&#238;n&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Structures d&#39;informations de d&#233;roulement cha&#238;n&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si l'indicateur UNW\_FLAG\_CHAININFO est défini, une structure d'information sur le déroulement constitue un indicateur secondaire, et le champ d'adresse partagé du gestionnaire d'exceptions\/des informations chaînées contient les informations de déroulement principales.  Le code suivant extrait les informations de déroulement principales, en supposant que `unwindInfo` est la structure dont l'indicateur UNW\_FLAG\_CHAININFO est défini.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 Les informations chaînées sont utiles dans deux situations.  En premier lieu, elles peuvent être utilisées pour les segments de code non contigus.  En utilisant des informations chaînées, vous pouvez réduire la taille des informations de déroulement requises, étant donné que vous n'avez pas à dupliquer le tableau de codes de déroulement de l'info de déroulement principale.  
  
 Vous pouvez également utiliser des informations chaînées pour grouper des sauvegardes de registre non rémanentes.  Le compilateur peut différer l'enregistrement de certains registres volatiles jusqu'à ce qu'il soit en dehors du prologue d'entrée de la fonction.  Vous pouvez enregistrer ceci en collectant des informations de déroulement principales pour la partie de la fonction avant le code groupé, puis en définissant les informations chaînées avec une taille de prologue non nulle, où les codes de déroulement dans les informations chaînées reflètent les enregistrements des registres non volatiles.  Dans ce cas, les codes de déroulement sont toutes les instances de UWOP\_SAVE\_NONVOL.  Un regroupement qui stocke les registres non\-volatiles à l'aide d'une TRANSMISSION DE TYPE PUSH ou de modifier le registre de RSP à l'aide d'une allocation de piles fixe supplémentaire n'est pas pris en charge.  
  
 Un élément UNWIND\_INFO pour lequel UNW\_FLAG\_CHAININFO est défini peut contenir une entrée RUNTIME\_FUNCTION comportant un élément UNWIND\_INFO dont la valeur NW\_FLAG\_CHAININFO est également définie \(rétraction multiple\).  Pour terminer, les pointeurs de l'info de déroulement chaînés arriveront à un élément UNWIND\_INFO dont UNW\_FLAG\_CHAININFO a été effacé ; il s'agit de l'élément UNWIND\_INFO principal qui pointe sur le point d'entrée de procédure réel.  
  
## Voir aussi  
 [Données de déroulement pour la gestion des exceptions et la prise en charge du débogueur](../build/unwind-data-for-exception-handling-debugger-support.md)