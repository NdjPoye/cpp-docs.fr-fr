---
title: Compilateur avertissement (niveau 1) C4945 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4945
dev_langs:
- C++
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d02583de0d4b986b2b723d3347d0aa0f212f4d16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4945"></a>Avertissement du compilateur (niveau 1) C4945
'symbole' : Impossible d’importer le symbole de 'assembly2' : car 'symbole' a déjà été importé à partir d’un autre assembly 'assembly1'  
  
 Un symbole a été importé à partir d’un assembly référencé, mais ce symbole a déjà été importé à partir d’un autre assembly référencé. Ne pas faire référence à un des assemblys ou le nom du symbole modifiée dans un des assemblys.  
  
 Les exemples suivants génèrent l’erreur C4945.  
  
```  
// C4945a.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 Et puis  
  
```  
// C4945b.cs  
// compile with: /target:library  
// C# source code to create a dll  
public class ClassA {  
   public int i;  
}  
```  
  
 Et puis  
  
```  
// C4945c.cpp  
// compile with: /clr /LD /W1  
#using "C4945a.dll"  
#using "C4945b.dll"   // C4945  
```