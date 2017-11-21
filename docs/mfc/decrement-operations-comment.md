---
title: "--Opérations commentaire | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 63b3d7a313f0f725444ba77612d8b53280393640
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="-operations-comment"></a>// Opérations, commentaires
La `// Operations` section d’une déclaration de classe MFC contient des fonctions de membre que vous pouvez appeler sur l’objet pour effectuer les opérations ou effectuer des actions (opérations). Ces fonctions sont généralement non -**const** , car ils ont généralement des effets secondaires. Ils peuvent être virtuelles ou non virtuelles selon les besoins de la classe. En règle générale, ces membres sont publics.  
  
 Dans l’exemple de liste à partir de la classe `CStdioFile`, dans [un exemple des commentaires](../mfc/an-example-of-the-comments.md), la liste inclut deux fonctions membres sous ce commentaire : `ReadString` et `WriteString`.  
  
 Comme avec les attributs, les opérations peuvent être subdivisées.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [Commentaire sur l’implémentation](../mfc/decrement-implementation-comment.md)   
 [Commentaire de constructeurs](../mfc/decrement-constructors-comment.md)   
 [Commentaire d’attributs](../mfc/decrement-attributes-comment.md)   
 [Remplaçable commentaire](../mfc/decrement-overridables-comment.md)

