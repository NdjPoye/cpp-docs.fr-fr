---
title: "Avertissement des outils &#201;diteur de liens LNK4253 | Microsoft Docs"
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
  - "LNK4253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4253"
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

section 'section1' non fusionnée dans 'section2' ;  elle est déjà fusionnée dans 'section3'  
  
 L'éditeur de liens a détecté des demandes de fusion multiples en conflit  L'éditeur de liens ignore l'une des demandes.  
  
 Une option ou directive **\/MERGE** a été rencontrée et la section `from` a déjà été fusionnée dans une section différente en raison d'une option ou directive **\/MERGE** antérieure \(ou d'une fusion implicite de l'éditeur de liens\).  
  
 Pour remédier à l'erreur LNK4253, supprimez l'une des demandes de fusion.  
  
 Lorsque vous ciblez des ordinateurs x86 et des cibles Windows CE \(ARM, MIPS, SH4 et Thumb\) avec Visual C\+\+, la section .CRT est désormais en lecture seule.  Si votre code dépend du comportement précédent \(les sections .CRT sont accessibles en lecture\/écriture\), un comportement inattendu risque de se produire.  
  
 Pour plus d'informations, consultez  
  
-   [\/MERGE \(Combiner des sections\)](../../build/reference/merge-combine-sections.md)  
  
-   [commentaire](../../preprocessor/comment-c-cpp.md)  
  
## Exemple  
 Dans l'exemple suivant, l'éditeur de liens est invité à fusionner la section `.rdata` à deux reprises, mais dans des sections différentes.  L'exemple suivant génère l'erreur LNK4253.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```