---
title: "Avertissement du compilateur (niveau 3) C4619 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4619"
ms.assetid: 701fea21-01aa-4bea-93d4-1cb8824170b0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma warning : numéro d'avertissement inexistant 'numéro'  
  
 Vous avez essayé de désactiver un avertissement qui n'existe pas.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4619 :  
  
```  
// C4619.cpp  
// compile with: /W3 /c  
#pragma warning(default : 4619)  
#pragma warning(disable : 4354)   // C4619, C4354 does not exist  
```