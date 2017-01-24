---
title: "Erreur irr&#233;cup&#233;rable C1104 | Microsoft Docs"
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
  - "C1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1104"
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur irrécupérable lors de l’importation de libid : 'message'  
  
 Le compilateur a détecté un problème d’importation d’une bibliothèque de types.  Par exemple, vous ne pouvez pas spécifier une bibliothèque de types avec libid et spécifier également `no_registry`.  
  
 Pour plus d'informations, consultez [\#import, directive](../../preprocessor/hash-import-directive-cpp.md).  
  
 L’exemple suivant génère l’erreur C1104 :  
  
```  
// C1104.cpp #import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104  
```