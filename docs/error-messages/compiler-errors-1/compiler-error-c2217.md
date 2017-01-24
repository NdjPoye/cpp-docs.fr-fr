---
title: "Erreur du compilateur C2217 | Microsoft Docs"
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
  - "C2217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2217"
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribut1' requiert 'attribut2'  
  
 Le premier attribut de fonction nécessite le deuxième attribut.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  La fonction d'interruption \(`__interrupt`\) est déclarée comme `near`.  Les fonctions d'interruption doivent être `far`.  
  
2.  Fonction d'interruption déclarée avec `__stdcall` ou `__fastcall`.  Les fonctions d'interruption doivent utiliser les conventions d'appel C.  
  
## Exemple  
 L'erreur C2217 peut également se produire si vous essayez de lier un délégué à une fonction CLR qui accepte un nombre variable d'arguments.  Si la fonction a également une surcharge de tableau param, utilisez\-la à la place.  L'exemple suivant génère l'erreur C2217 :  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```