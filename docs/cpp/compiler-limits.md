---
title: "Limites du compilateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, limites des constructions de langage"
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Limites du compilateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La norme C\+\+ recommande certaines limites pour diverses constructions de langage.  La liste suivante indique les cas où le compilateur Visual C\+\+ n'implémente pas les limites recommandées.  Le premier nombre est la limite établie dans la norme ISO C\+\+ 11 \(INCITS\/ISO\/IEC 14882\-2011\[2012\], Annexe B\) et le deuxième nombre est la limite implémentée par Visual C\+\+ :  
  
-   Niveaux d'imbrication des instructions composées, structures de contrôle des itérations et structures de contrôle des sélections \[norme C\+\+ : 256\] \(compilateur Visual C\+\+ : dépend de la combinaison des instructions imbriquées, mais généralement entre 100 et 110\).  
  
-   Paramètres dans une seule définition macro \[norme C\+\+ : 256\] \(compilateur Visual C\+\+ : 127\).  
  
-   Arguments dans une seule invocation macro \[norme C\+\+ : 256\] \(compilateur Visual C\+\+ : 127\).  
  
-   Caractères d'un littéral de chaîne\/caractère ou d'un littéral de chaîne étendu \(après concaténation\) \[norme C\+\+ : 65536\] \(compilateur Visual C\+\+ : 65 535 caractères codés sur un octet, y compris la marque de fin `null` et 32 767 caractères codés sur deux octets, y compris la marque de fin `null`\).  
  
-   Niveaux de définitions de classe, de structure ou d'union imbriquées dans un même argument `struct-declaration-list` \[norme C\+\+ : 256\] \(compilateur Visual C\+\+ : 16\).  
  
-   Initialiseurs membres dans une définition de constructeur \[norme C\+\+ : 6 144\] \(compilateur Visual C\+\+ : au moins 6144\).  
  
-   Qualifications de portée d'un seul identificateur \[norme C\+\+ : 256\] \(compilateur Visual C\+\+ : 127\).  
  
-   Spécifications `extern` imbriquées \[norme C\+\+ : 1 024\] \(compilateur Visual C\+\+ : 9, sans compter la spécification `extern` implicite dans la portée globale, ou 10, en comptant la spécification `extern` implicite dans la portée globale\).  
  
-   Arguments de modèle dans une déclaration de modèle \[norme C\+\+ : 1 024\] \(compilateur Visual C\+\+ : 2 046\).  
  
## Voir aussi  
 [Comportement non standard](../cpp/nonstandard-behavior.md)