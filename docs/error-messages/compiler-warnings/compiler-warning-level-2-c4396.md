---
title: "Avertissement du compilateur (niveau&#160;2) C4396 | Microsoft Docs"
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
  - "C4396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4396"
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;2) C4396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'nom' : le spécificateur inline ne peut pas être utilisé lorsqu’une déclaration friend se réfère à une spécialisation d’un modèle de fonction  
  
 Une spécialisation d’un modèle de fonction ne peut spécifier aucun des spécificateurs [inline](../../misc/inline-inline-forceinline.md). Le compilateur émet l’avertissement C4396 et ignore le spécificateur inline.  
  
### Pour corriger cette erreur  
  
-   Supprimez le spécificateur `inline`, `__inline` ou `__forceinline` de la déclaration de la fonction friend.  
  
## Exemple  
 L’exemple de code suivant montre une déclaration de fonction friend non valide avec un spécificateur `inline`.  
  
```  
// C4396.cpp // compile with: /W2 /c class X; template<class T> void Func(T t, int i); class X { friend inline void Func<char>(char t, int i);  //C4396 // try the following line instead //    friend void Func<char>(char t, int i); int i; };  
```