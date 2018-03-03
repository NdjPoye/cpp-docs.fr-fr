---
title: "LNK4254 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e17bcd03f92114c1b7cd21e63220cf6372c17bf2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4254"></a>Avertissement des outils Éditeur de liens LNK4254
section 'section1' (offset) fusionnée dans 'section2' (offset) avec des attributs différents  
  
 Le contenu d’une section ont été fusionné dans un autre, mais les attributs des deux sections sont différents. Votre programme peut provoquer des résultats inattendus. Par exemple, vous souhaitez lire des données uniquement peuvent maintenant être dans une section accessible en écriture.  
  
 Pour résoudre l’erreur LNK4254, modifier ou supprimer la demande de fusion.  
  
 Lorsque vous ciblez x86 ordinateurs et des cibles Windows CE (ARM, MIPS, SH4 et Thumb) avec Visual C++, le. CRT est en lecture seule. Si votre code dépend du comportement précédent (. CRT sont en lecture/écriture), vous pouvez constater un comportement inattendu.  
  
 Pour plus d'informations, consultez  
  
-   [/Merge (combiner des Sections)](../../build/reference/merge-combine-sections.md)  
  
-   [commentaire (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur LNK4254.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```