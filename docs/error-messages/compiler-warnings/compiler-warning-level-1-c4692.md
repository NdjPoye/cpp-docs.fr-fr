---
title: "Avertissement du compilateur (niveau&#160;1) C4692 | Microsoft Docs"
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
  - "C4692"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4692"
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4692
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la signature de membre non privée contient un type natif privé d'assembly 'type\_natif'  
  
 Un type visible à l'extérieur de l'assembly contient une fonction membre dont la signature comprend un type natif qui n'est pas visible à l'extérieur de l'assembly.  Par conséquent, la fonction membre ne doit pas être appelée si son type conteneur est instancié à l'extérieur de l'assembly.  
  
 Pour plus d'informations, consultez [Visibilité du type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4692 :  
  
```  
// C4692.cpp  
// compile with: /W1 /c /clr  
#pragma warning(default:4692)  
class Private_Native_Class {};  
public class Public_Native_Class {};  
public ref class Public_Ref_Class {  
public:  
   void Test(Private_Native_Class *) {}   // C4692  
   void Test2(Public_Native_Class *) {}   // OK  
};  
```