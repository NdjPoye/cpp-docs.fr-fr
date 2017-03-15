---
title: "Erreur du compilateur C3398 | Microsoft Docs"
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
  - "C3398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3398"
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : impossible de convertir de 'function\_signature' en 'function\_pointer'. L'expression source doit être un symbole de fonction  
  
 Quand la convention d’appel [\_\_clrcall](../../cpp/clrcall.md) n’est pas spécifiée lors de la compilation avec **\/clr**, le compilateur génère deux points d’entrée \(adresses\) pour chaque fonction : un point d’entrée natif et un point d’entrée managé.  
  
 Par défaut, le compilateur retourne le point d’entrée natif, mais dans certains cas, il est souhaitable d’avoir un point d’entrée managé \(par exemple, lors de l’assignation de l’adresse à un pointeur de fonction `__clrcall`\). Pour que le compilateur puisse choisir de manière fiable le point d’entrée managé dans une assignation, le côté droit doit être un symbole de fonction.