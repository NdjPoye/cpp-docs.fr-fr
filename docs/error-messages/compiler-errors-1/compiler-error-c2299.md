---
title: "Erreur du compilateur C2299 | Microsoft Docs"
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
  - "C2299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2299"
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : changement de comportement : une spécialisation explicite ne peut pas être un constructeur de copie ou un opérateur d'assignation de copie  
  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual C\+\+ 2005 : les versions antérieures de Visual C\+\+ autorisaient les spécialisations explicites pour un constructeur de copie ou un opérateur d'assignation de copie.  
  
 Pour remédier à l'erreur C2299, n'utilisez pas un constructeur de copie ou un opérateur d'assignation comme fonction de modèle, mais plutôt comme fonction sans modèle qui prend un type de classe.  Tout code qui appelle le constructeur de copie ou l'opérateur d'assignation en spécifiant explicitement les arguments template doit supprimer ces derniers.  
  
 L'exemple suivant génère l'erreur C2299 :  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```