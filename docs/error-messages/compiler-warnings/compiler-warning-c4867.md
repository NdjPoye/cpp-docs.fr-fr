---
title: "Avertissement du compilateur C4867 | Microsoft Docs"
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
  - "C4867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4867"
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : liste d'arguments manquante dans l'appel de fonction ; utilisez 'appel' pour créer un pointeur vers membre  
  
 Un pointeur vers une fonction membre n'a pas été correctement initialisé.  
  
 Cet avertissement peut être dû à la mise en conformité du compilateur pour Visual C\+\+ 2005 : conformité pointeur vers membre améliorée.  Le code compilé avant Visual C\+\+ 2005 génère à présent l'erreur C4867.  
  
 Cet avertissement est toujours émis en tant qu'erreur.  Utilisez le pragma [warning](../../preprocessor/warning.md) pour désactiver cet avertissement.  Pour plus d'informations sur l'erreur C4867 et MFC\/ATL, consultez [\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4867 :  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```