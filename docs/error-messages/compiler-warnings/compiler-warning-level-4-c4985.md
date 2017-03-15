---
title: "Avertissement du compilateur (niveau&#160;4) C4985 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4985"
ms.assetid: 832f001c-afe7-403d-a8b4-02334724c79e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4985
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol name' : attributs absents de la déclaration précédente.  
  
 Les annotations du langage d’annotation de code source Microsoft \(SAL\) dans la définition ou la déclaration de méthode actuelle diffèrent des annotations d’une déclaration précédente. Les mêmes annotations SAL doivent être utilisées dans la définition et les déclarations d’une méthode.  
  
 Le langage d’annotation de code source Microsoft \(SAL\) propose un ensemble d’annotations qui décrivent la manière dont une fonction exploite ses paramètres, les hypothèses qu’elle émet à leur sujet et les garanties apportées lors de la finition. Les annotations sont définies dans le fichier d’en\-tête sal.h.  
  
 Notez que les macros SAL ne sont pas développées sauf si l’indicateur [\/analyze](../../build/reference/analyze-code-analysis.md) est spécifié pour le projet. Quand vous spécifiez **\/analyze**, le compilateur peut lever l’avertissement C4985, même si aucun avertissement ni aucune erreur n’est apparu sans **\/analyze**.  
  
### Pour corriger cette erreur  
  
1.  Utilisez les mêmes annotations SAL dans la définition d’une méthode et toutes ses déclarations.  
  
## Voir aussi  
 [Annotations SAL](../../c-runtime-library/sal-annotations.md)