---
title: "Avertissement du compilateur (niveau 1) C4917 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4917"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4917"
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4917
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'déclarateur' : un GUID ne peut être associé qu'à une classe, une interface ou un espace de noms  
  
 Une structure définie par l'utilisateur ne peut pas avoir de GUID s'il ne s'agit pas d'une [classe](../../cpp/class-cpp.md), d'une [interface](../../cpp/interface.md) ou d'un [espace de noms](../../misc/namespace-declaration.md).  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple de code suivant génère C4917 :  
  
```  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```