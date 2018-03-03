---
title: "--Commentaire d’attributs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18a142cc0434e0e09e69d9bffc30826c461cf185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="-attributes-comment"></a>// Attributs, commentaire
La `// Attributes` section d’une déclaration de classe MFC contient les attributs (ou propriétés) publics de l’objet. En général, il s’agit de variables membres ou fonctions Get/Set. Les fonctions « Get » et « Set » peuvent ou ne peuvent pas être virtuelles. Les fonctions « Get » sont généralement **const**, car dans la plupart des cas ils n’ont pas d’effets secondaires. Ces membres sont normalement publiques ; attributs protégés et privés sont généralement détectées dans la section d’implémentation.  
  
 Dans l’exemple de liste à partir de la classe `CStdioFile`, sous [un exemple des commentaires](../mfc/an-example-of-the-comments.md), la liste inclut une variable membre, `m_pStream`. Classe `CDC` répertorie près de 20 membres sous ce commentaire.  
  
> [!NOTE]
>  Grandes classes, telles que `CDC` et `CWnd`, ne peuvent avoir des membres autant qui simplement répertoriant tous les attributs d’un groupe ajouteriez pas beaucoup plus de clarté. Dans ce cas, la bibliothèque de classes utilise les autres commentaires comme en-têtes pour délimiter davantage les membres. Par exemple, `CDC` utilise `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`et bien plus encore. Les groupes qui représentent les attributs suit la syntaxe habituelle décrite ci-dessus. Nombreuses classes OLE possèdent une section d’implémentation appelée `// Interface Maps`.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [Commentaire sur l’implémentation](../mfc/decrement-implementation-comment.md)   
 [Commentaire de constructeurs](../mfc/decrement-constructors-comment.md)   
 [Commentaire d’opérations](../mfc/decrement-operations-comment.md)   
 [Remplaçable commentaire](../mfc/decrement-overridables-comment.md)

