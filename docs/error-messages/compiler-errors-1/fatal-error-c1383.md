---
title: "Erreur irr&#233;cup&#233;rable C1383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1383"
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur irr&#233;cup&#233;rable C1383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'option du compilateur \/GL est incompatible avec la version installée du Common Language Runtime  
  
 L’erreur C1383 se produit quand vous utilisez une version précédente du Common Language Runtime avec un compilateur plus récent et quand vous compilez avec **\/clr** et **\/GL.**  
  
 Pour corriger, n’utilisez pas **\/GL** avec **\/clr** ou installez la version du Common Language Runtime fournie avec votre compilateur.  
  
 Pour plus d’informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) et [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md).