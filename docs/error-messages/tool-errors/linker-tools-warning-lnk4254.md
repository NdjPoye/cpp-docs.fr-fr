---
title: "Avertissement des outils &#201;diteur de liens LNK4254 | Microsoft Docs"
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
  - "LNK4254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4254"
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

section 'section1' \(offset\) fusionnée dans 'section2' \(offset\) avec des attributs différents  
  
 Le contenu d'une section a été fusionné dans celui d'un autre, mais les attributs des deux sections sont différents.  Votre programme peut produire des résultats inattendus.  Par exemple, les données que vous souhaitiez en lecture seule peuvent désormais se trouver dans une section accessible en écriture.  
  
 Pour remédier à l'erreur LNK4254, modifiez ou supprimez la demande de fusion.  
  
 Lorsque vous ciblez des ordinateurs x86 et des cibles Windows CE \(ARM, MIPS, SH4 et Thumb\) avec Visual C\+\+, la section .CRT est en lecture seule.  Si votre code dépend du comportement précédent \(les sections .CRT sont accessibles en lecture\/écriture\), un comportement inattendu risque de se produire.  
  
 Pour plus d'informations, consultez  
  
-   [\/MERGE \(Combiner des sections\)](../../build/reference/merge-combine-sections.md)  
  
-   [commentaire](../../preprocessor/comment-c-cpp.md)  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK4254.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```