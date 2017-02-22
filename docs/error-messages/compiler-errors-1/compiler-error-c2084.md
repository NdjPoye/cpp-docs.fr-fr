---
title: "Erreur du compilateur C2084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2084"
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la fonction 'fonction' a déjà un corps  
  
 La fonction a déjà été définie.  
  
 Dans les versions précédentes de Visual C\+\+,  
  
-   Le compilateur acceptait plusieurs spécialisations de modèle correspondant au même type, bien que des définitions supplémentaires n'étaient jamais disponibles.  Le compilateur détecte maintenant ces définitions multiples  
  
-   \_\_int32 et int étaient traités comme des types séparés.  Le compilateur traite maintenant \_\_int32 comme un synonyme d'int.  Cela signifie que le compilateur détecte plusieurs définitions si une fonction est surchargée sur \_\_int32 et int, et génère une erreur.  
  
 L'exemple suivant génère l'erreur C2084 :  
  
```  
// C2084.cpp  
void Func(int);  
void Func(int) {}   // define function  
void Func(int) {}   // C2084 second definition  
```  
  
 Résolution possible :  
  
```  
// C2084b.cpp  
// compile with: /c  
void Func(int);  
void Func(int) {}  
```