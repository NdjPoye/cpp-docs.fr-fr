---
title: "Avertissement du compilateur C4962 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4962"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4962"
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4962
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : les optimisations guidées par profil sont désactivées, car elles génèrent des incohérences au niveau des données de profil  
  
 Une fonction n’a pas été compilée avec \/LTCG:PGO, car les données de décompte \(profil\) pour la fonction n’étaient pas fiables. Réexécutez le profilage pour régénérer le fichier .pgc qui contient les données de profil non fiables pour cette fonction.  
  
 Cet avertissement est désactivé par défaut. Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).