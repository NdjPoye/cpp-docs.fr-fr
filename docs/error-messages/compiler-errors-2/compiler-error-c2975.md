---
title: "Erreur du compilateur C2975 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2975"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2975"
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur du compilateur C2975
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : argument template non valide pour 'type', expression constante évaluée au moment de la compilation attendue  
  
 L'argument template ne correspond pas à la déclaration du modèle, une expression constante devrait figurer entre les crochets.  Vous ne pouvez pas utiliser de variables comme arguments réels du modèle.  Vérifiez la définition du modèle pour trouver les types corrects.  
  
 L'exemple suivant génère l'erreur C2975 :  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 L'erreur C2975 se produira également si vous utilisez \_\_LINE\_\_ comme constante évaluée au moment de la compilation avec [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md).  Une solution serait de compiler avec [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) au lieu de **\/ZI**.  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```