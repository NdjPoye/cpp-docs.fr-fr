---
title: "Du compilateur (niveau 1) d’avertissement C4274 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4274
dev_langs: C++
helpviewer_keywords: C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4519258a10937ad96528f34484a44d398a0cd0ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4274"></a>Du compilateur (niveau 1) d’avertissement C4274
\#Ident ignorée ; consultez la documentation pour #pragma comment (exestr, 'string')  
  
 La `#ident` directive, qui insère une chaîne spécifiée par l’utilisateur dans l’objet ou le fichier exécutable, est déconseillée. Par conséquent, le compilateur ignore la directive.  
  
> [!CAUTION]
>  C4274 d’avertissement vous indique d’utiliser le [#pragma comment (exestr, 'string')](../../preprocessor/comment-c-cpp.md) la directive. Toutefois, ce Conseil est déconseillé et sera être modifié dans une prochaine version du compilateur. Si vous utilisez la `#pragma` directive, l’outil de l’éditeur de liens (LINK.exe) ignore l’enregistrement de commentaires généré par la directive et émet un avertissement [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md). Au lieu du `#ident` directive, nous vous recommandons d’utiliser une chaîne de ressource de version de fichier dans votre application.  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Supprimer le `#ident "` *chaîne* `"` la directive.  
  
## <a name="see-also"></a>Voir aussi  
 [commentaire (C/C++)](../../preprocessor/comment-c-cpp.md)   
 [Outils de l’éditeur de liens LNK4229 d’avertissement](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)   
 [Utilisation des fichiers de ressources](../../windows/working-with-resource-files.md)