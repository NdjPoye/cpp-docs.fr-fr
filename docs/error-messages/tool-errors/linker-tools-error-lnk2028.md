---
title: "Erreur des outils &#201;diteur de liens LNK2028 | Microsoft Docs"
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
  - "LNK2028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2028"
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"fonction\_exportée" \(nom\_décoré\) référencée dans la fonction "fonction\_contenant\_l'appel\_de\_fonction" \(nom\_décoré\)  
  
 Lors d'une tentative d'importation d'une fonction native dans une image pure, n'oubliez pas que les conventions d'appel implicites diffèrent entre les compilations natives et pures.  
  
## Exemple  
 Cet exemple de code génère un composant avec une fonction native exportée dont la convention d'appel est implicitement [\_\_cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## Exemple  
 L'exemple suivant crée un client pure qui utilise la fonction native.  Toutefois, la convention d'appel sous **\/clr:pure** est [\_\_clrcall](../../cpp/clrcall.md).  L'exemple suivant génère l'erreur LNK2028.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```