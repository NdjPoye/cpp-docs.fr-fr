---
title: "Avertissement du compilateur (niveau&#160;1) C4041 | Microsoft Docs"
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
  - "C4041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4041"
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

limite du compilateur : arrêt de la sortie de l’explorateur  
  
 Les informations du navigateur dépassent la limite du compilateur.  
  
 Cet avertissement peut être dû à une compilation avec [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) \(informations du navigateur comprenant des variables locales\).  
  
### Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Compilez avec \/Fr \(informations du navigateur sans variables locales\).  
  
2.  Désactivez la sortie de navigateur \(compilez sans \/FR ou \/Fr\).