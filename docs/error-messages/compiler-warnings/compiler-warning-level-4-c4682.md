---
title: "Avertissement du compilateur (niveau&#160;4) C4682 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4682"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4682"
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau&#160;4) C4682
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter' : aucun attribut de paramètre directionnel spécifié, \[in\] pris par défaut  
  
 Une méthode sur un paramètre dans une interface avec attributs ne possède pas l’un des attributs directionnels [in](../../windows/in-cpp.md) ou [out](../../windows/out-cpp.md). Le paramètre par défaut est in.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 L’exemple suivant génère l’avertissement C4682 :  
  
```  
// C4682.cpp // compile with: /W4 #pragma warning(default : 4682) #include <windows.h> [module(name="MyModule")]; [ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ] __interface IMyIface : IUnknown { HRESULT f1(int i, int *pi); // C4682 // try the following line // HRESULT f1([in] int i, [in] int *pi); }; int main() { }  
```