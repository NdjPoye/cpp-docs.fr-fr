---
title: "Erreur du compilateur C3163 | Microsoft Docs"
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
  - "C3163"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3163"
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3163
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'construction' : attributs non cohérents avec la déclaration qui précède  
  
 Le ou les attributs appliqués à une définition entrent en conflit avec le ou les attributs appliqués à une déclaration.  
  
 Pour résoudre l'erreur C3163, l'une des solutions consiste à éliminer les attributs de la déclaration anticipée.  Les attributs d'une déclaration anticipée doivent être égaux ou inférieurs aux attributs de la définition.  
  
 Le langage d'annotation de code source \(SAL\) Microsoft est une des causes possibles de l'erreur C3163.  Les macros SAL ne sont pas extensibles à moins que vous ne compiliez votre projet à l'aide de l'indicateur **\/analyze**.  Un programme dont la compilation s'effectue correctement sans \/analyze peut lever l'exception C3163 si vous tentez de le recompiler avec l'option \/analyze.  Pour plus d'informations concernant SAL, consultez [Annotations SAL](../../c-runtime-library/sal-annotations.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3163.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## Voir aussi  
 [Annotations SAL](../../c-runtime-library/sal-annotations.md)