---
title: "Erreur irr&#233;cup&#233;rable C1021 | Microsoft Docs"
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
  - "C1021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1021"
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Commande de préprocesseur non valide 'chaîne'  
  
 `string` n’est pas une [directive de préprocesseur](../../preprocessor/preprocessor-directives.md) valide. Pour résoudre cette erreur, utilisez un nom de préprocesseur valide pour `string`.  
  
 L’exemple suivant génère l’erreur C1021 :  
  
```  
// C1021.cpp #BadPreProcName    // C1021 delete line  
```