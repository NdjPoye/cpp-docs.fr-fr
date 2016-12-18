---
title: "Avertissement du compilateur (niveau 4) C4232 | Microsoft Docs"
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
  - "C4232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4232"
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : 'identificateur' : adresse de dllimport 'dllimport' non static, identité non garantie  
  
 Sous les extensions Microsoft \(\/Ze\), vous pouvez donner une valeur non statique comme adresse d'une fonction déclarée avec le modificateur **dllimport**.  Sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\), ceci génère une erreur.  
  
 L'exemple suivant génère l'erreur C4232 :  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```