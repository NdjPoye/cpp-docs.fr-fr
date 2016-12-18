---
title: "Avertissement du compilateur (niveau&#160;1) C4620 | Microsoft Docs"
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
  - "C4620"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4620"
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4620
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

aucune forme suffixée de l’opérateur 'operator \+\+' trouvée pour le type 'type' ; utilisez la forme préfixée  
  
 Aucun opérateur d’incrément postfix n’est défini pour le type donné. Le compilateur a utilisé l’opérateur de préfixe surchargé.  
  
 Pour éviter cet avertissement, vous pouvez définir un opérateur `++` postfix. Créez une version à deux arguments de l’opérateur `++`, comme indiqué ici :  
  
```  
// C4620.cpp // compile with: /W1 class A { public: A(int nData) : m_nData(nData) { } A operator++() { m_nData -= 1; return *this; } // A operator++(int) // { //    A tmp = *this; //    m_nData -= 1; //    return tmp; // } private: int m_nData; }; int main() { A a(10); ++a; a++;   // C4620 }  
```