---
title: "Instructions d&#39;it&#233;ration (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "instructions d'itération"
  - "structures de boucle, instructions d'itération"
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instructions d&#39;it&#233;ration (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les instructions d'itération entraînent une exécution des instructions \(ou des instructions composées\) zéro ou plusieurs fois, compte tenu de certains critères de terminaison des boucles.  Lorsque ces instructions sont des instructions composées, elles sont exécutées dans l'ordre, sauf lorsque l'instruction [break](../cpp/break-statement-cpp.md) ou l'instruction [continue](../cpp/continue-statement-cpp.md) est détectée.  
  
 C\+\+ fournit quatre instructions d'itération : [while](../cpp/while-statement-cpp.md), [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) et [range\-based for](../cpp/range-based-for-statement-cpp.md).  Chacune itère jusqu'à ce que l'expression d'arrêt ait la valeur zéro \(false\), ou jusqu'à ce que la boucle d'arrêt soit forcée avec une instruction **break**.  Le tableau suivant résume ces instructions et leurs actions ; chacune est décrit en détail dans les sections suivantes.  
  
### Instructions d'itération  
  
|Instruction|Évaluée en|Initialisation|Incrémentation|  
|-----------------|----------------|--------------------|--------------------|  
|`while`|Début de boucle|Non|Non|  
|**do**|Fin de boucle|Non|Non|  
|**for**|Début de boucle|Oui|Oui|  
|**range\-based for**|Début de boucle|Oui|Oui|  
  
 La partie instruction d'une instruction d'itération ne peut pas être une déclaration.  Toutefois, il peut s'agir d'une instruction composée contenant une déclaration.  
  
## Voir aussi  
 [Vue d'ensemble des instructions C\+\+](../cpp/overview-of-cpp-statements.md)