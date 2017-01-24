---
title: "Erreur du compilateur C2785 | Microsoft Docs"
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
  - "C2785"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2785"
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2785
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'déclaration1' et 'déclaration2' ont des types de retour différents  
  
 Le type de retour de la spécialisation du modèle de fonction diffère de celui du modèle de fonction principal.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez la cohérence de toutes les spécialisations du modèle de fonction.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2785 :  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```