---
title: "Avertissement du compilateur (niveau 4) C4366 | Microsoft Docs"
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
  - "C4366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4366"
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le résultat de l'opérateur 'opérateur' unaire risque de ne pas être aligné  
  
 Si un membre de structure n'est pas aligné en raison d'une compression, le compilateur vous avertit que l'adresse de ce membre est assignée à un pointeur aligné.  Par défaut, tous les pointeurs règles sont alignés.  
  
 Pour remédier à l'erreur C4366, modifiez l'alignement de la structure ou déclarez le pointeur avec le mot clé [\_\_unaligned](../../cpp/unaligned.md).  
  
 Pour plus d'informations, consultez \_\_unaligned et [pack](../../preprocessor/pack.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4366 :  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```