---
title: "Erreur du compilateur C3382 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3382"
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'sizeof' n'est pas pris en charge avec \/clr:safe  
  
 Le fichier de sortie d’une compilation **\/clr:safe** est un fichier de type sécurisé vérifiable. De plus, sizeof n’est pas pris en charge, car la valeur de retour de l’opérateur sizeof est size\_t, dont la taille varie selon le système d’exploitation.  
  
 Pour plus d'informations, consultez  
  
-   [sizeof, opérateur](../../cpp/sizeof-operator.md)  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Problèmes courants de migration vers Visual C\+\+ 64 bits](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Exemple  
 L’exemple suivant génère l’erreur C3382 :  
  
```  
// C3382.cpp // compile with: /clr:safe int main() { sizeof( char );   // C3382 }  
```