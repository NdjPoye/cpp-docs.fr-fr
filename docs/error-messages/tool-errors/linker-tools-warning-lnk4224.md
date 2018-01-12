---
title: "LNK4224 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4224
dev_langs: C++
helpviewer_keywords: LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96399e0c66eb3cb719073b2318513cd680723d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4224"></a>Avertissement des outils Éditeur de liens LNK4224
option n’est plus pris en charge ; ignoré  
  
 Une option de l’éditeur de liens obsolètes, non valide a été spécifiée et est ignorée.  
  
 Par exemple, LNK4224 peut se produire si une directive /comment apparaît dans. obj. La directive /comment aurait été ajoutée via les [commentaire (C/C++)](../../preprocessor/comment-c-cpp.md) pragma, à l’aide de l’option exestr déconseillée. Utilisez dumpbin [/tous les](../../build/reference/all.md) pour afficher les directives de l’éditeur de liens dans un fichier .obj.  
  
 Si possible, modifiez la source pour le fichier .obj et supprimez le pragma. Si vous ignorez cet avertissement, il est possible qu’un .executable compilé avec **/CLR : pure** ne fonctionnera pas comme prévu.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur LNK4224.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```