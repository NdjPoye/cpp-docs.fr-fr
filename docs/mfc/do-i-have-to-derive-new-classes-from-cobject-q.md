---
title: "Dois-je d&#233;river les nouvelles classes de CObject&#160;? | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject (classe), quand utiliser"
  - "classes dérivées, de CObject"
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Dois-je d&#233;river les nouvelles classes de CObject&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Non, vous ne devez pas.  
  
 Dérivez une classe d' [CObject](../mfc/reference/cobject-class.md) lorsque vous avez besoin des fonctionnalités qu'elle contient, telles que la creatability de sérialisation ou la creatability dynamique.  De nombreuses classes de données doivent être sérialisées aux fichiers, ainsi il est souvent judicieux de les dériver d' `CObject`.  Pour obtenir un exemple d'une classe dérivée d' `CObject`, consultez [Exemple de dessin à main levée](../top/visual-cpp-samples.md).  
  
## Voir aussi  
 [Classe CObject : Forum Aux Questions](../mfc/cobject-class-frequently-asked-questions.md)