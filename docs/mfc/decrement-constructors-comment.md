---
title: --Commentaire de constructeurs | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 25b6ebff4108b47e70b34aa6d83293bede78ee97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="-constructors-comment"></a>// Constructeurs, commentaire
La `// Constructors` section d’une déclaration de classe MFC déclare des constructeurs (dans le sens C++), ainsi que toutes les fonctions d’initialisation requises pour utiliser réellement l’objet. Par exemple, `CWnd::Create` est dans la section des constructeurs car avant d’utiliser le `CWnd` de l’objet, il doit être « entièrement construit » en appelant le constructeur C++ d’abord, puis le **créer** (fonction). En règle générale, ces membres sont publics.  
  
 Par exemple, la classe `CStdioFile` a trois constructeurs, dont est indiqué dans la liste sous [un exemple des commentaires](../mfc/an-example-of-the-comments.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Commentaire sur l’implémentation](../mfc/decrement-implementation-comment.md)   
 [Commentaire d’attributs](../mfc/decrement-attributes-comment.md)   
 [Commentaire d’opérations](../mfc/decrement-operations-comment.md)   
 [Remplaçable commentaire](../mfc/decrement-overridables-comment.md)

