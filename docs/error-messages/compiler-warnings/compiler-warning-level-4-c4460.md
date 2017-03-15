---
title: "Avertissement du compilateur (niveau 4) C4460 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4460"
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Avertissement du compilateur (niveau 4) C4460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

paramètre de l'opérateur WinRT ou CLR 'opérateur' passé par référence.L'opérateur WinRT ou CLR 'opérateur' a une sémantique différente de celle de l'opérateur C\+\+ 'opérateur', voulez\-vous effectuer un passage par valeur ?  
  
 Vous avez passé une valeur par référence à un opérateur CLR ou Windows Runtime défini par l'utilisateur.  Si la valeur est modifiée dans la fonction, notez que la valeur de retour de la fonction sera attribuée à la valeur retournée après l'appel de fonction.  En C\+\+ standard, la valeur modifiée est reflétée après l'appel de fonction.  
  
## Exemple  
 L'exemple suivant génère l'avertissement C4460 et montre comment le corriger.  
  
```  
// C4460.cpp  
// compile with: /W4 /clr   
#include <stdio.h>  
  
public value struct V {  
   static V operator ++(V& me) {   // C4460  
   // try the following line instead  
   // static V operator ++(V me) {  
  
      printf_s(__FUNCSIG__ " called\n");  
      V tmp = me;  
      me.m_i++;  
      return tmp;  
   }  
   int m_i;  
};  
  
int main() {  
   V v;  
   v.m_i = 0;  
  
   printf_s("%d\n", v.m_i);   // Should print 0  
   v++;   // Translates to "v = V::operator ++(v)"  
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning  
}  
```