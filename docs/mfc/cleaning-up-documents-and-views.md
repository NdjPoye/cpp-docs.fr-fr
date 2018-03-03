---
title: Nettoyage des Documents et vues | Documents Microsoft
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
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a95193d5ca3df890c9c97f458b76413e588bc59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-documents-and-views"></a>Nettoyage des documents et vues
Lors de la fermeture d’un document, le framework appelle d’abord son [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) fonction membre. Si vous avez alloué de la mémoire dans le segment de mémoire au cours de l’utilisation du document, `DeleteContents` est le meilleur endroit pour la libérer.  
  
> [!NOTE]
>  Vous ne devez pas libérer les données de document dans le destructeur du document. Dans le cas d’une application SDI, l’objet de document peut être réutilisé.  
  
 Vous pouvez remplacer le destructeur d’une vue pour libérer toute mémoire allouée dans le tas.  
  
## <a name="see-also"></a>Voir aussi  
 [Initialisation et nettoyage des documents et vues](../mfc/initializing-and-cleaning-up-documents-and-views.md)

