---
title: "Avertissement du compilateur (niveau 1) C4490 | Microsoft Docs"
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
  - "C4490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4490"
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override' : utilisation incorrecte du spécificateur de substitution ; 'fonction' ne correspond pas à une méthode de classe ref de base  
  
 Un spécificateur de substitution n'a pas été utilisé correctement.  Par exemple, vous ne substituez pas une fonction d'interface, mais vous l'implémentez.  
  
 Pour plus d'informations, consultez [Spécificateurs de substitution](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4490 :  
  
```  
// C4490.cpp  
// compile with: /clr /c /W1  
  
interface struct IFace {  
   void Test();  
};  
  
ref struct Class1 : public IFace {  
   virtual void Test() override {}   // C4490  
   // try the following line instead  
   // virtual void Test() {}  
};  
```