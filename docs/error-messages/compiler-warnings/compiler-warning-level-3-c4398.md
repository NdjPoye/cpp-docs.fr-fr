---
title: "Avertissement du compilateur (niveau 3) C4398 | Microsoft Docs"
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
  - "C4398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4398"
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : un objet global par processus risque de ne pas fonctionner correctement avec plusieurs appdomains ; utilisez \_\_declspec\(appdomain\) à la place  
  
 Une fonction virtuelle avec la convention d'appel [\_\_clrcall](../../cpp/clrcall.md) dans un type natif provoque la création d'un vtable par domaine d'application.  Une telle variable risque de ne pas fonctionner correctement en cas d'utilisation dans plusieurs domaines d'application.  
  
 Vous pouvez résoudre cet avertissement en compilant avec **\/clr:pure**, afin de définir par défaut les variables globales par appdomain, ou en marquant la variable `__declspec(appdomain)` explicitement.  
  
 Pour plus d’informations, consultez [appdomain](../../cpp/appdomain.md) et [Domaines d'application et Visual C\+\+](../../dotnet/application-domains-and-visual-cpp.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4398 :  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```