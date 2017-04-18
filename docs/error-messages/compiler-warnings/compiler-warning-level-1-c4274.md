---
title: Compilateur avertissement (niveau 1) C4274 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4274
dev_langs:
- C++
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: fbba1e6dde180e77afe7ed8960849ee8cc0fd108
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4274"></a>Compilateur avertissement (niveau 1) C4274
\#Ident ignoré ; consultez la documentation pour #pragma comment (exestr, 'string')  
  
 La `#ident` directive, qui insère une chaîne spécifiée par l’utilisateur dans l’objet ou le fichier exécutable, est déconseillée. Par conséquent, le compilateur ignore la directive.  
  
> [!CAUTION]
>  C4274 d’avertissement vous conseille d’utiliser la [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md) la directive. Toutefois, ce Conseil est déconseillé et est modifié dans une prochaine version du compilateur. Si vous utilisez la `#pragma` directive, l’outil de l’éditeur de liens (LINK.exe) ignore l’enregistrement de commentaires produit par la directive et émet un avertissement [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Au lieu de la `#ident` directive, nous vous recommandons d’utiliser une chaîne de ressource de version de fichier dans votre application.  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Supprimer le `#ident "` *chaîne* `"` la directive.  
  
## <a name="see-also"></a>Voir aussi  
 [commentaire (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Outils de l’éditeur de liens LNK4229 d’avertissement](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Utilisation des fichiers de ressources](../../windows/working-with-resource-files.md)
