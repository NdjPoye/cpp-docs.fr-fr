---
title: "Erreur du compilateur C2270 | Microsoft Docs"
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
  - "C2270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2270"
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : modificateurs non autorisés sur les fonctions non membres  
  
 Une fonction non membre est déclarée avec un modificateur [const](../../cpp/const-cpp.md), [volatile](../../cpp/volatile-cpp.md) ou autre modificateur de modèle de mémoire.  
  
 L'exemple suivant génère l'erreur C2270 :  
  
```  
// C2270.cpp  
// compile with: /c  
void func1(void) const;   // C2270, nonmember function  
  
void func2(void);  
  
class CMyClass {  
public:  
   void func2(void) const;  
};  
```