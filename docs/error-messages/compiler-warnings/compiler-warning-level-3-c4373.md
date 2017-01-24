---
title: "Avertissement du compilateur (niveau&#160;3) C4373 | Microsoft Docs"
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
  - "C4373"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4373"
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;3) C4373
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'%$S' : la fonction virtuelle se substitue à '%$pS', les versions précédentes n’ont pas été substituées lorsque les paramètres ne différaient que par les qualificateurs const\/volatile  
  
 Votre application contient une méthode dans une classe dérivée qui remplace une méthode virtuelle dans une classe de base, et les paramètres de la méthode de substitution ne diffèrent des paramètres de la méthode virtuelle que par un qualificateur [const](../../cpp/const-cpp.md) ou [volatile](../../cpp/volatile-cpp.md). Cela signifie que le compilateur doit lier une référence de fonction à la méthode dans la classe de base ou dans la classe dérivée.  
  
 Les versions du compilateur antérieures à [!INCLUDE[cpp_orcas_long](../../cpp/includes/cpp_orcas_long_md.md)] lient la fonction à la méthode dans la classe de base, puis émettent un message d’avertissement. Les versions suivantes du compilateur ignorent le qualificateur `const` ou `volatile`, lient la fonction à la méthode dans la classe dérivée, puis émettent l’avertissement `C4373`. Ce dernier comportement est conforme à la norme C\+\+.  
  
## Exemple  
 L’exemple de code suivant génère l’avertissement C4373.  
  
```  
// c4373.cpp // compile with: /c /W3 #include <stdio.h> struct Base { virtual void f(int i) { printf("base\n"); } }; struct Derived : Base { void f(const int i) {  // C4373 printf("derived\n"); } }; void main() { Derived d; Base* p = &d; p->f(1); }  
```  
  
```Output  
dérivés  
```