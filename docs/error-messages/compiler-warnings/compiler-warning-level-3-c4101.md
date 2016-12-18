---
title: "Avertissement du compilateur (niveau 3) C4101 | Microsoft Docs"
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
  - "C4101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4101"
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : variable locale non référencée  
  
 La variable locale n'est jamais utilisée.  Cet avertissement apparaît dans la situation évidente :  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 Mais cet avertissement peut aussi apparaître lors de l'appel d'une fonction membre **static** par une instance de la classe :  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 Dans ce cas, le compilateur utilise les informations concernant `si` pour accéder à la fonction **static**, mais l'instance de la classe n'est pas nécessaire pour appeler la fonction **static** ; d'où l'avertissement.  Pour éviter cet avertissement, vous pouvez :  
  
-   Ajouter un constructeur, dans lequel le compilateur utilise l'instance de `si` pour l'appel à `func`.  
  
-   Supprimer le mot clé **static** de la définition de `func`.  
  
-   Appeler explicitement la fonction **static** : `int y = S::func();`.