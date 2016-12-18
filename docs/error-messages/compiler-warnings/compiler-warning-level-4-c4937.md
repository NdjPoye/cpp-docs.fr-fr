---
title: "Avertissement du compilateur (niveau&#160;4) C4937 | Microsoft Docs"
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
  - "C4937"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4937"
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4937
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de distinguer 'text1' et 'text2' comme arguments de 'directive'  
  
 Compte tenu de la méthode utilisée par le compilateur pour traiter les arguments aux directives, il est impossible de différencier les noms qui ont une signification pour le compilateur, notamment les mots clés avec plusieurs représentations textuelles \(formes à un ou deux traits de soulignement\).  
  
 \_\_cdecl et \_\_forceinline sont des exemples de ces chaînes.  Sous \/Za, notez que seules les formes à deux traits de soulignement sont activées.  
  
 L’exemple suivant génère l’avertissement C4937 :  
  
```  
// C4937.cpp // compile with: /openmp /W4 #include "omp.h" int main() { #pragma omp critical ( __leave )   // C4937 ; // OK #pragma omp critical ( leave ) ; }  
```