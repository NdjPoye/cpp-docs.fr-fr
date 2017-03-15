---
title: "Erreur du compilateur C3807 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3807"
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une classe avec l'attribut ComImport ne peut pas dériver de 'type2', seule l'implémentation d'interface est autorisée  
  
 Un type dérivé de <xref:System.Runtime.InteropServices.ComImportAttribute> ne peut implémenter qu'une interface.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3807 :  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```