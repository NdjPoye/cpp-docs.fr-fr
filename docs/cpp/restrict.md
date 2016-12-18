---
title: "restrict | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "restrict"
  - "restrict_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), restrict"
  - "restrict __declspec (mot clé)"
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# restrict
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appliqué à une déclaration ou une définition de fonction qui retourne un type pointeur et indique au compilateur que la fonction retourne un objet qui n'aura pas comme alias un autre pointeur.  
  
## Syntaxe  
  
```  
__declspec(restrict) return_type f();  
```  
  
## Notes  
 Le compilateur propage `__declspec(restrict)`.  Par exemple, la fonction CRT `malloc` est décorée avec `__declspec(restrict)`. Par conséquent, les pointeurs initialisés à des emplacements de mémoire avec `malloc` sont également supposés ne pas avoir d'alias.  
  
 Le compilateur ne vérifie pas que le pointeur n'a pas réellement d'alias.  Il incombe au développeur de s'assurer que le programme n'attribue pas d'alias à un pointeur marqué avec le modificateur `restrict __declspec`.  
  
 Pour plus d'informations sur la sémantique semblable concernant les variables, consultez [\_\_restrict](../cpp/extension-restrict.md).  
  
## Exemple  
 Pour obtenir un exemple utilisant `restrict`, consultez [noalias](../cpp/noalias.md).  
  
 Pour plus d'informations sur le mot clé restrict qui fait partie de C\+\+ AMP, consultez [restrict \(C\+\+ AMP\)](../cpp/restrict-cpp-amp.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)