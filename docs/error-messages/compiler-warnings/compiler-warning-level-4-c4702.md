---
title: "Avertissement du compilateur (niveau 4) C4702 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4702"
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau 4) C4702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'atteindre le code  
  
 Cet avertissement résulte de la mise en conformité de Visual Studio .NET 2003 : code inaccessible.  Lorsque le compilateur \(back end\) détecte un code inaccessible, il génère C4702, avertissement de niveau 4.  
  
 Pour produire un code valide dans les versions Visual Studio .NET 2003 et Visual Studio .NET de Visual C\+\+, retirez le code inaccessible ou assurez\-vous que tout le code source est accessible par un flux d'exécution.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4702 :  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## Exemple  
 Lors de la compilation avec **\/GX**, **\/EHc**, **\/EHsc** ou  **\/EHac** et de l'utilisation de fonctions extern C, le code peut devenir inaccessible, car ces dernières sont censées ne pas lever d'exception ; par conséquent, le bloc catch n'est pas accessible.  S'il vous semble que cet avertissement n'est pas valide parce qu'une fonction peut lever une exception, compilez avec **\/EHa** ou **\/EHs**, selon l'exception levée.  
  
 Pour plus d'informations, consultez [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md).  
  
 L'exemple suivant génère l'erreur C4702 :  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```