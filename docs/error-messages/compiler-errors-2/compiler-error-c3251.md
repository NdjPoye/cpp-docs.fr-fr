---
title: "Erreur du compilateur C3251 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3251"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3251"
ms.assetid: 541c163e-5ee9-457c-a1e5-da860788b10d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3251
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'appeler une méthode de classe de base sur une instance de type valeur  
  
 L’erreur suivante se produit, car `GetClass` est membre de `Microsoft.Runtime.Object` et non de `Microsoft.Runtime.Integer4`.