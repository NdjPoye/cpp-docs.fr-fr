---
title: LNK4224 d’avertissement des outils Éditeur de liens | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a051e341a22871b4229617b3958cb68dedc2921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
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