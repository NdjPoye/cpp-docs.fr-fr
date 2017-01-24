---
title: "Avertissement du compilateur (niveau&#160;3) C4638 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4638"
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;3) C4638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

commentaire de document XML : référence à un symbole inconnu 'symbol'  
  
 Le compilateur n’a pas pu résoudre un symbole \(***symbole***\). Le symbole doit être valide dans la compilation.  
  
 L’exemple suivant génère l’avertissement C4638 :  
  
```  
// C4638.cpp // compile with: /clr /doc /LD /W3 using namespace System; /// Text for class MyClass. public ref class MyClass { public: /// <summary> Text </summary> /// <see cref="aSymbolThatAppearsNowhereInMyProject"/> // Try the following line instead: // /// <see cref="System::Console::WriteLine"/> void MyMethod() {} };   // C4638  
```