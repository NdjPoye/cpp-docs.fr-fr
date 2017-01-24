---
title: "/Zc:auto (d&#233;duire le type de variable) | Microsoft Docs"
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
  - "/Zc:auto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (options du compilateur C++)"
  - "déduire le type de variable (C++)"
  - "Zc (options du compilateur C++)"
  - "-Zc (options du compilateur C++)"
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:auto (d&#233;duire le type de variable)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'option de compilateur **\/Zc:auto\[\-\]** indique au compilateur comment utiliser le [mot clé auto](../../cpp/auto-keyword.md) pour déclarer des variables.  Si vous spécifiez l'option par défaut, **\/Zc:auto**, le compilateur déduit le type de la variable déclarée de son expression d'initialisation.  Si vous spécifiez  **\/Zc:auto\-**, le compilateur alloue la variable à la classe de stockage automatique.  
  
## Syntaxe  
  
```  
/Zc:auto[-]  
```  
  
## Notes  
 Le standard C\+\+ définit une signification originale et une autre révisée pour le mot clé `auto`.  Avant [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], le mot clé déclarait une variable dans la classe de stockage automatique ; c'est\-à\-dire, une variable qui avait une durée de vie locale.  Depuis [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)] déjà, le mot clé déduit le type d'une variable à partir de l'expression d'initialisation de la déclaration. Utilisez l'option de compilateur **\/Zc:auto\[\-\]** pour indiquer au compilateur d'utiliser la signification originale ou révisée du mot clé `auto`.  
  
 Le compilateur émet un message de diagnostic approprié si votre usage du mot clé `auto` contredit l'option de compilateur actuelle.  Pour plus d'informations, voir [auto, mot clé](../../cpp/auto-keyword.md).  Pour plus d'informations sur les problèmes de conformité avec Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option de compilateur dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le nœud **Propriétés de configuration**.  
  
3.  Cliquez sur le nœud **C\/C\+\+**.  
  
4.  Cliquez sur le nœud **Ligne de commande**.  
  
5.  Ajoutez **\/Zc:auto** ou **\/Zc:auto\-** dans le volet **Options supplémentaires :**.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)   
 [auto, mot clé](../../cpp/auto-keyword.md)