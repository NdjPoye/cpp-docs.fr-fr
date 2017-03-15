---
title: "Avertissement du compilateur (niveau&#160;3) C4622 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4622"
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;3) C4622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Remplacement des informations de débogage formées lors de la création de l’en\-tête précompilé du fichier objet : 'fichier'  
  
 Les informations CodeView dans le fichier spécifié ont été perdues lorsqu’il a été compilé avec l’option [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) \(utiliser des en\-têtes précompilés\).  
  
 Renommez le fichier objet \(à l’aide de [\/Fo](../../build/reference/fo-object-file-name.md)\) lors de la création ou de l’utilisation du fichier d’en\-tête précompilé et établissez une liaison avec le nouveau fichier objet.