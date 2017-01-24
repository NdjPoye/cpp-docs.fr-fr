---
title: "Avertissement du compilateur (niveau 4) C4571 | Microsoft Docs"
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
  - "C4571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4571"
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Informations : la sémantique catch\(...\) a changé depuis Visual C\+\+ 7.1 ; les exceptions structurées \(SEH\) ne sont plus interceptées  
  
 L'erreur C4571 est générée pour chaque bloc catch\(...\) lors de la compilation avec **\/EHs**.  
  
 Lors de la compilation avec **\/EHs**, un bloc catch\(...\) n'intercepte pas d'exception structurée \(division par zéro ou pointeur null, par exemple\) ; un bloc catch\(...\) n'intercepte que les exceptions C\+\+ levées de manière explicite.  Pour plus d'informations, consultez [Gestion des exceptions](../../cpp/exception-handling-in-visual-cpp.md).  
  
 Cet avertissement est désactivé par défaut.  Activez cet avertissement pour garantir que lors d'une compilation avec **\/EHs**, vos blocs catch\(...\) ne vont pas intercepter des exceptions structurées.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Pour résoudre l'erreur C4571, procédez de l'une des manières suivantes :  
  
-   Compilez avec **\/EHa** si vous souhaitez que vos blocs catch\(...\) interceptent les exceptions structurées.  
  
-   N'activez pas l'erreur C4571 si vous ne souhaitez pas que vos blocs catch\(...\) interceptent les exceptions structurées, mais si vous désirez néanmoins utiliser les blocs catch\(...\).  Vous pouvez toujours intercepter les exceptions structurées à l'aide des mots clés de gestion des exceptions structurées \(**\_\_try**, **\_\_except**et **\_\_finally**\).  Cependant, n'oubliez pas qu'une fois compilés, les destructeurs **\/EHs** ne sont appelés que lorsqu'une exception C\+\+ est levée, et non lorsqu'une exception SEH se produit.  
  
-   Remplacez le bloc catch\(...\) par des blocs catch pour des exceptions C\+\+ spécifiques, et ajoutez éventuellement la gestion des exceptions structurées autour de la gestion des exceptions C\+\+ \(**\_\_try**, **\_\_except** et **\_\_finally**\).  Pour plus d'informations, consultez [Gestion structurée des exceptions](../../cpp/structured-exception-handling-c-cpp.md).  
  
 Pour plus d'informations, consultez [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4571 :  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```