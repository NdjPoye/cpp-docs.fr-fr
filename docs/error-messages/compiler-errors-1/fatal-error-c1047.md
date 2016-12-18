---
title: "Erreur irr&#233;cup&#233;rable C1047 | Microsoft Docs"
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
  - "C1047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1047"
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le fichier objet ou le fichier bibliothèque 'fichier' a été créé à l’aide d’un compilateur antérieur à celui d’autres objets ; régénérez les objets et bibliothèques obsolètes  
  
 L’erreur C1047 se produit quand des fichiers objets ou des bibliothèques générés à l’aide de la commande **\/LTCG** sont liés entre eux, alors qu’ils ont été créés avec des versions différentes de l’ensemble d’outils Visual C\+\+.  
  
 Cela peut se produire si vous commencez à utiliser une nouvelle version du compilateur sans avoir effectué de régénération propre des fichiers objets ou des bibliothèques existants.  
  
 Pour résoudre l’erreur C1047, régénérez tous les fichiers objets et bibliothèques.