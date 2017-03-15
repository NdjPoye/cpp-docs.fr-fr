---
title: "Avertissement du compilateur C4687 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4687"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4687"
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Avertissement du compilateur C4687
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une classe abstraite sealed ne peut pas implémenter une interface 'interface'  
  
 Un type abstrait sealed n'est généralement utile que pour stocker des fonctions membres static.  
  
 Pour plus d'informations, consultez [abstract](../../windows/abstract-cpp-component-extensions.md) et [sealed](../../windows/sealed-cpp-component-extensions.md).  
  
 Par défaut, C4687 est émis en tant qu'erreur.  Vous pouvez supprimer l'erreur C4687 avec le pragma [warning](../../preprocessor/warning.md).  Si vous êtes certain de souhaiter implémenter une interface dans un type abstrait sealed, vous pouvez supprimer l'erreur C4687.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4687 :  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```