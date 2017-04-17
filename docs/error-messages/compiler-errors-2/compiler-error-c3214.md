---
title: "Erreur du compilateur C3214 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3214"
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : argument de type non valide pour le paramètre générique 'paramètre' du générique 'type\_générique', ne satisfait pas la contrainte 'contrainte'  
  
 Le type a été spécifié pour une instanciation d’une classe générique qui ne satisfait pas à la contrainte de la classe générique.  
  
 L’exemple suivant génère l’erreur C3214 :  
  
```  
// C3214.cpp // compile with: /clr interface struct A {}; generic <class T> where T : A ref class C {}; ref class X : public A {}; int main() { C<int>^ c = new C<int>;   // C3214 C<X ^> ^ c2 = new C<X^>;   // OK }  
```