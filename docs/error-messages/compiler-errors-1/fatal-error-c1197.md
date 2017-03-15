---
title: "Erreur irr&#233;cup&#233;rable C1197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1197"
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable C1197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de référencer 'mscorlib.dll\_1', car le programme a déjà référencé 'mscorlib.dll\_2'  
  
 Le compilateur correspond à une version du Common Language Runtime.  Toutefois, vous avez tenté de référencer une version d'un fichier du Common Language Runtime à partir d'une version antérieure.  
  
 Pour résoudre cette erreur, ne référencez que des fichiers de la version du Common Language Runtime fournie avec la version de Visual C\+\+ avec laquelle vous compilez.  
  
## Exemple  
 L'exemple suivant génère l'erreur C1197 :  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```