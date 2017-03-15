---
title: "Compiler Error C2921 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2921"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2921"
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compiler Error C2921
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

redéfinition : 'classe' : classe modèle ou générique en cours de redéclaration comme 'type'  
  
 Une classe générique ou de modèle possède plusieurs déclarations qui ne sont pas équivalentes.  Pour corriger cette erreur, utilisez des noms différents pour des types différents ou supprimez la redéfinition du nom de type.  
  
 L'exemple suivant génère l'erreur C2921 :  
  
```  
// C2921.cpp  
// compile with: /c  
template <class T> struct TC2 {};  
typedef int TC2;   // C2921  
// try the following line instead  
// typedef struct TC2<int> x;   // OK - declare a template instance   
```  
  
 L'erreur C2921 peut également se produire lors de l'utilisation de génériques.  
  
```  
// C2921b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC2 {};  
typedef int GC2;   // C2921  
// try the following line instead  
// typedef ref struct GC2<int> x;  
```