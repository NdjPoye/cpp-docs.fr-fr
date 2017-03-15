---
title: "Avertissement du compilateur (niveau&#160;1) C4036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4036"
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Avertissement du compilateur (niveau&#160;1) C4036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' sans nom comme paramètre réel  
  
 Une structure, union, énumération ou classe utilisée comme paramètre réel n’a pas reçu de nom de type. Si vous utilisez [\/Zg](../../build/reference/zg-generate-function-prototypes.md) pour générer des prototypes de fonction, le compilateur émet cet avertissement et met en commentaire le paramètre formel dans le prototype généré.  
  
 Spécifiez un nom de type pour remédier à cet avertissement.  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4036.  
  
```  
// C4036.c // compile with: /Zg /W1 // D9035 expected typedef struct { int i; } T; void f(T* t) {}   // C4036 // OK typedef struct MyStruct { int i; } T2; void f2(T2 * t) {}  
```