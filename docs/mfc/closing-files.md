---
title: Fermeture de fichiers | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27b1c59c952b022c7382db7d6b2dcb660cca2e9a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="closing-files"></a>Fermeture des fichiers
Comme d’habitude dans les opérations d’e/s, une fois que vous avez terminé avec un fichier, vous devez le fermer.  
  
#### <a name="to-close-a-file"></a>Pour fermer un fichier  
  
1.  Utilisez le **fermer** fonction membre. Cette fonction ferme le fichier de système de fichiers et vide les mémoires tampons si nécessaire.  
  
 Si vous avez alloué la [CFile](../mfc/reference/cfile-class.md) objet sur le frame (comme dans l’exemple illustré [ouverture de fichiers](../mfc/opening-files.md)), l’objet sera automatiquement être fermé et puis détruits lorsqu’il devient hors de portée. Notez que la suppression du `CFile` objet ne supprime pas le fichier physique du système de fichiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers](../mfc/files-in-mfc.md)

