---
title: "Avertissement des outils &#201;diteur de liens LNK4078 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4078"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4078"
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Avertissement des outils &#201;diteur de liens LNK4078
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

plusieurs sections 'nom de la section' trouvées avec différents attributs  
  
 LINK a trouvé deux ou plusieurs sections de même nom avec des attributs différents.  
  
 Cet avertissement peut être généré si une bibliothèque d'importation ou un fichier d'exportation a été créé avec une version précédente de LINK ou LIB.  
  
 Recréez le fichier et recommencez l'édition de liens.  
  
## Exemple  
 L'erreur LNK4078 peut également être provoquée par une modification avec rupture : la section nommée par [init\_seg](../../preprocessor/init-seg.md) sur x86 était en lecture\/écriture ; elle est désormais en lecture seule.  
  
 L'exemple suivant génère l'erreur LNK4078.  
  
```  
// LNK4078.cpp  
// compile with: /W1  
// LNK4078 expected  
#include <stdio.h>  
#pragma warning(disable : 4075)  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors to call  
PF pfx[200];   // pointers to destructors.  
  
struct A { A() {} };  
  
int myexit (PF pf) { return 0; }  
  
#pragma section(".mine$a", read, write)  
// try the following line instead  
// #pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) int ii = 1;  
  
#pragma section(".mine$z", read, write)  
// try the following line instead  
// #pragma section(".mine$z", read)  
__declspec(allocate(".mine$z")) int i = 1;  
  
#pragma data_seg()  
#pragma init_seg(".mine$m", myexit)  
A bbbb;   
A cccc;  
int main() {}  
```