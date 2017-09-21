---
title: "Avertissement du compilateur (niveau 1) C4544 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4544"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4544"
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4544
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'déclaration' : argument template par défaut ignoré sur cette déclaration de modèle  
  
 Un argument template par défaut a été spécifié dans un emplacement incorrect et a été ignoré.  Un argument template par défaut pour un modèle de classe peut uniquement être spécifié dans la déclaration ou la définition du modèle de classe et non sur un membre du modèle de classe.  
  
 Cet exemple génère l'erreur C4545 et l'exemple suivant montre comment résoudre le problème :  
  
```  
// C4544.cpp  
// compile with: /W1 /LD  
template <class T>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T=int>  
template <class T1>  
struct S<T>::S1 {};   // C4544  
```  
  
 Dans cet exemple, le paramètre par défaut s'applique au modèle de classe `S` :  
  
```  
// C4544b.cpp  
// compile with: /LD  
template <class T = int>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T>  
template <class T1>  
struct S<T>::S1 {};  
```