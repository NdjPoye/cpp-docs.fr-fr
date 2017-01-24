---
title: "Avertissement du compilateur (niveau 1) C4342 | Microsoft Docs"
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
  - "C4342"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4342"
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4342
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

modification de comportement : 'fonction' appelé, mais un opérateur de membre a été appelé dans les versions précédentes  
  
 Dans les versions antérieures de Visual C\+\+, un membre était appelé, mais ce comportement a été modifié et le compilateur recherche désormais la meilleure correspondance dans la portée de l'espace de noms.  
  
 Auparavant, si un opérateur membre était détecté, le compilateur ne tenait compte d'aucun opérateur de la portée de l'espace de noms.  S'il existe une meilleure correspondance dans la portée de l'espace de noms, le compilateur actuel l'appelle correctement, alors que les compilateurs antérieurs ne la prenaient pas en compte.  
  
 Cet avertissement doit être désactivé lorsque vous avez porté votre code vers la version actuelle.  Le compilateur peut fournir des faux positifs, en générant cet avertissement pour du code qui ne comprend aucun changement de comportement.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4342 :  
  
```  
// C4342.cpp  
// compile with: /EHsc /W1  
#include <fstream>  
#pragma warning(default: 4342)  
using namespace std;  
struct X : public ofstream {  
   X();  
};  
  
X::X() {  
   open( "ofs_bug_ev.txt." );  
   if ( is_open() ) {  
      *this << "Text" << "<-should be text" << endl;   // C4342  
      *this << ' ' << "<-should be space symbol" << endl;   // C4342  
   }  
}  
  
int main() {  
   X b;  
   b << "Text" << "<-should be text" << endl;  
   b << ' ' << "<-should be space symbol" << endl;  
}  
```