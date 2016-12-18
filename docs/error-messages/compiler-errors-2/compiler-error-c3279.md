---
title: "Erreur du compilateur C3279 | Microsoft Docs"
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
  - "C3279"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3279"
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3279
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les spécialisations partielles et explicites, ainsi que les instanciations explicites des modèles de classe déclarés dans l'espace de noms cli sont interdites  
  
 L’espace de noms `cli` est défini par Microsoft et contient des pseudo\-modèles. Le compilateur Visual C\+\+ n’autorise pas les spécialisations partielles et explicites définies par l’utilisateur, ni les instanciations de modèles de classe dans cet espace de noms.  
  
 L’exemple suivant génère l’erreur C3279 :  
  
```  
// C3279.cpp // compile with: /clr namespace cli { template <> ref class array<int> {};   // C3279 template <typename T> ref class array<T, 2> {};   // C3279 }  
```