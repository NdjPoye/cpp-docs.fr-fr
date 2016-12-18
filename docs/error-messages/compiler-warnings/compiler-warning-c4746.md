---
title: "Avertissement du compilateur C4746 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4746
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'accès volatile de '\<expression\>' dépend du paramètre \/volatile:\[iso&#124;ms\] ; envisagez d'utiliser les fonctions intrinsèques \_\_iso\_volatile\_load\/store.  
  
 L'erreur C4746 est émis lorsqu'une variable volatile est accessible.  Il est conçu pour aider les développeurs à identifier les emplacements de code affectés par le modèle spécifique de volatiles actuellement spécifié \(qui peut être contrôlé par l'option du compilateur de [\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) \).  En particulier, il peut être utile en recherchant les cloisonnements générés par le compilateur de mémoire de matériel lorsque \/volatile:ms est utilisé.  
  
 Les intrinsèques de \_\_iso\_volatile\_load\/store peuvent être utilisées pour accéder explicitement à la mémoire volatile sans subir le modèle volatiles.  Ces intrinsèques ne génère pas d'erreur C4746.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).