---
title: "Erreur du compilateur C3669 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3669"
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C3669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : spécificateur de substitution 'override' non autorisé sur les fonctions membres ou les constructeurs static  
  
 Une substitution n'a pas été spécifiée correctement.  Pour plus d'informations, consultez [Substitutions explicites](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3669 :  
  
```  
// C3669.cpp  
// compile with: /clr  
public ref struct R {  
   R() override {}   // C3669  
};  
```