---
title: "conform | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "conform_CPP"
  - "vc-pragma.conform"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "conform (pragma)"
  - "forScope conform (pragma)"
  - "pragmas, conform"
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# conform
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie le comportement au moment de l'exécution de l'option du compilateur [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  
  
## Syntaxe  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### Paramètres  
 *name*  
 Spécifie le nom de l'option du compilateur à modifier.  Le seul *name* valide est `forScope`.  
  
 **show** \(facultatif\)  
 Entraîne l'affichage du paramètre actuel de *name* \(true ou false\) via un message d'avertissement au moment de la compilation.  Par exemple, `#pragma conform(forScope, show)`.  
  
 **on, off**\(facultatif\)  
 La définition de *name* sur **on** active l'option du compilateur [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  La valeur par défaut est **off**.  
  
 **push** \(facultatif\)  
 Pousse la valeur actuelle de *name* dans la pile interne du compilateur.  Si vous spécifiez *identifier*, vous pouvez spécifier la valeur **on** ou **off** pour que *name* fasse l'objet d'un push dans la pile.  Par exemple, `#pragma conform(forScope, push, myname, on)`.  
  
 **pop** \(facultatif\)  
 Définit la valeur de *name* sur la valeur en haut de la pile interne du compilateur, puis dépile la pile.  Si l'identificateur est spécifié avec **pop**, la pile est alors dépilée jusqu'à ce qu'il trouve l'enregistrement avec *identifier*, qui sera également dépilé. La valeur actuelle de *name* dans l'enregistrement suivant sur la pile devient la nouvelle valeur de *name*.  Si vous spécifiez pop avec un *identifier* qui n'est pas un enregistrement sur la pile, **pop** est ignoré.  
  
 *identifier*\(facultatif\)  
 Peut être inclus avec une commande **push** ou **pop**.  Si *identifier* est utilisé, un spécificateur **on** ou **off** peut également être utilisé.  
  
## Exemple  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)