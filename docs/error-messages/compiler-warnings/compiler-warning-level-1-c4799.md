---
title: "Avertissement du compilateur (niveau 1) C4799 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4799"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4799"
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4799
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aucune instruction EMMS à la fin de la fonction 'fonction'  
  
 La fonction comprend au moins une instruction MMX, mais ne possède pas d'instruction EMMS.  Lorsque vous utilisez une instruction multimédia, vous devez également utiliser une instruction EMMS pour annuler le mot de la balise multimédia à la fin du code MMX.  Pour plus d'informations sur les instructions EMMS, consultez [Guidelines for When to Use EMMS](http://msdn.microsoft.com/fr-fr/a0c3b1e4-01a4-419c-a58f-ff1e97dea7d3).  
  
 L'avertissement C4799 peut apparaître lorsque vous utilisez ivec.h, indiquant que le code n'emploie pas correctement l'exécution de l'instruction EMMS avant le retour.  Il s'agit d'un avertissement erroné pour ces en\-têtes.  Vous pouvez désactiver ceux\-ci en définissant \_SILENCE\_IVEC\_C4799 dans ivec.h.  Sachez toutefois que cela empêchera le compilateur de fournir de façon appropriée des avertissements de ce type.  
  
 Pour obtenir des informations connexes, consultez l'option [Intel's MMX Instruction Set](../../assembler/inline/intel-s-mmx-instruction-set.md).