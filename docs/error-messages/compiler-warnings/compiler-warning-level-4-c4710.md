---
title: "Avertissement du compilateur (niveau 4) C4710 | Microsoft Docs"
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
  - "C4710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4710"
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : fonction non inline  
  
 La fonction donnée a été sélectionnée pour l'expansion inline, mais le compilateur n'a pas effectué la fonctionnalité inline.  
  
 La fonctionnalité inline est appliquée à la discrétion du compilateur.  Le mot clé **inline**, tout comme le mot clé **register**, est utilisé comme indicateur pour le compilateur.  Le compilateur emploie des heuristiques pour déterminer s'il doit appliquer la fonctionnalité inline à une fonction particulière afin d'accélérer le code lors d'une compilation visant à rendre l'exécution plus rapide ou s'il doit appliquer la fonctionnalité inline à une fonction particulière pour rendre le code plus petit lors d'une compilation visant à occuper moins d'espace.  Le compilateur n'appliquera la fonctionnalité inline aux fonctions très petites que lorsque la compilation est effectuée en vue d'un gain d'espace.  
  
 Dans certains cas, le compilateur n'appliquera pas la fonctionnalité inline à une fonction particulière pour des raisons mécaniques.  Consultez [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) pour une liste des raisons pour lesquelles le compilateur peut ne pas appliquer la fonctionnalité inline à une fonction.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).