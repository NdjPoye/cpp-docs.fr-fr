---
title: "Erreur du compilateur C3295 | Microsoft Docs"
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
  - "C3295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3295"
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\#pragma pragma' ne peut être utilisé qu’au niveau de la portée globale ou de la portée espace de noms  
  
 Certains pragmas ne peuvent pas être utilisés dans une fonction.  Pour plus d'informations, voir [Directives pragma et mot clé \_Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3295.  
  
```  
// C3295.cpp int main() { #pragma managed   // C3295 }  
```