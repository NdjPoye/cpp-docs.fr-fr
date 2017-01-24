---
title: "Avertissement du compilateur (niveau&#160;1) C4461 | Microsoft Docs"
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
  - "C4461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4461"
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : cette classe a un finaliseur 'finaliseur' mais pas de destructeur 'dtor'  
  
 La présence d'un finaliseur dans un type implique des ressources à supprimer.  À moins qu'un finaliseur soit appelé explicitement à partir du destructeur du type, le Common Language Runtime détermine à quel moment exécuter le finaliseur, une fois votre objet hors de portée.  
  
 Si vous définissez un destructeur dans le type et appelez explicitement le finaliseur à partir du destructeur, vous pouvez exécuter votre finaliseur de façon déterministe.  
  
 Pour plus d'informations, consultez [Destructeurs et finaliseurs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4461 :  
  
```  
// C4461.cpp  
// compile with: /W1 /clr /c  
ref class A {  
protected:  
   !A() {}   // C4461  
};  
  
// OK  
ref struct B {  
   ~B() {  
      B::!B();  
   }  
  
   !B() {}  
};  
```