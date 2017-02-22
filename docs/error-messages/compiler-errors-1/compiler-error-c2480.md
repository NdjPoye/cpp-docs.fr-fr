---
title: "Erreur du compilateur C2480 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2480"
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : 'thread' n'est valide que pour les éléments de données d'étendue static  
  
 Vous ne pouvez pas utiliser l'attribut `thread` avec une variable automatique, une donnée membre non statique, un paramètre de fonction ou sur des déclarations ou des définitions de fonction.  
  
 Utilisez l'attribut `thread` pour les variables globales, les données membres statiques et les variables statiques locales uniquement.  
  
 L'exemple suivant génère l'erreur C2480 :  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```