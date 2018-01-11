---
title: "--Commentaire sur l’implémentation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 437b091b2237c7219a0afeee46d78164751e6d3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="-implementation-comment"></a>// Commentaire sur l'implémentation
Le `// Implementation` section est la partie la plus importante de toute déclaration de classe MFC.  
  
 Cette section contient tous les détails d’implémentation. Les variables membres et les fonctions membres peuvent apparaître dans cette section. Tout élément sous cette ligne peut changer dans une future version de MFC. À moins que vous ne pouvez pas l’éviter, vous fiez pas aux détails ci-dessous le `// Implementation` ligne. En outre, les membres déclarés en dessous de la ligne d’implémentation ne sont pas documentés, bien qu’une implémentation est décrite dans les notes techniques. Les substitutions de fonctions virtuelles dans la classe de base résident dans cette section, quelle que soit la section la fonction de la classe de base est définie, car le fait qu’une fonction substitue l’implémentation de classe de base est considéré comme un détail d’implémentation. En règle générale, ces membres sont protégés, mais pas toujours.  
  
 Notez à partir de la `CStdioFile` sous [un exemple des commentaires](../mfc/an-example-of-the-comments.md) que les membres déclarés sous le `// Implementation` commentaire peut être déclaré comme **public**, `protected`, ou `private`. Vous devez uniquement utiliser ces membres avec précaution, car elles peuvent changer dans le futur. Déclaration d’un groupe de membres en tant que **public** peut s’avérer nécessaire pour l’implémentation de bibliothèque de classe fonctionne correctement. Toutefois, cela ne signifie pas que vous pouvez utiliser en toute sécurité des membres déclarées.  
  
> [!NOTE]
>  Vous pouvez trouver les commentaires, les autres types au-dessus ou au-dessous de la `// Implementation` commentaire. Dans les deux cas, elles décrivent les types de membres déclarés sous eux. S’ils apparaissent sous la `// Implementation` de commentaire, vous devez supposer que les membres peuvent changer dans les futures versions de MFC.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [Commentaire de constructeurs](../mfc/decrement-constructors-comment.md)   
 [Commentaire d’attributs](../mfc/decrement-attributes-comment.md)   
 [Commentaire d’opérations](../mfc/decrement-operations-comment.md)   
 [Remplaçable commentaire](../mfc/decrement-overridables-comment.md)

