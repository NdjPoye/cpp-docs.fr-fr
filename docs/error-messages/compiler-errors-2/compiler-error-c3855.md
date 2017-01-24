---
title: "Erreur du compilateur C3855 | Microsoft Docs"
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
  - "C3855"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3855"
ms.assetid: ed90f8c0-4154-4243-b066-493913df5727
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3855
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : le paramètre de type 'param' est incompatible avec la déclaration  
  
 Le compilateur a détecté des paramètres génériques ou de modèle avec des noms différents.  Cette situation peut se produire lorsqu'un paramètre de modèle spécifié dans la définition d'une spécialisation de modèle est incompatible avec sa déclaration.  
  
 L'exemple suivant génère l'erreur C3855 :  
  
```  
// C3855.cpp  
template <int N>  
struct C {  
   void f();  
};  
  
template <char N>  
void C<N>::f() {}   // C3855  
```  
  
 Résolution possible :  
  
```  
// C3855b.cpp  
// compile with: /c  
template <int N>  
struct C {  
   void f();  
};  
  
template <int N>  
void C<N>::f() {}  
```  
  
 L'erreur C3855 peut également se produire lors de l'utilisation de génériques :  
  
```  
// C3855c.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T>  
generic <class U>  
generic <class V>  
ref struct GC1<T>::GC2 { };   // C3855  
```  
  
 Résolution possible :  
  
```  
// C3855d.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC1 {  
   generic <class U>  
   ref struct GC2;  
};  
  
generic <class T>  
generic <class U>  
ref struct GC1<T>::GC2 { };  
```