---
title: "Erreur du compilateur C2441 | Microsoft Docs"
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
  - "C2441"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2441"
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2441
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : un symbole déclaré avec \_\_declspec\(process\) doit être const en mode \/clr:pure  
  
 Par défaut, les variables sont par domaine d'application sous **\/clr:pure**.  Une variable marquée `__declspec(process)` sous **\/clr:pure** est susceptible d'entraîner des erreurs si elle est modifiée dans un domaine d'application et lue dans un autre.  
  
 Par conséquent, le compilateur applique `const` aux variables par processus sous **\/clr:pure**, afin qu'elles soient en lecture seule dans tous les domaines d'application.  
  
 Pour plus d’informations, consultez [processus](../../cpp/process.md) et [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2441 :  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```