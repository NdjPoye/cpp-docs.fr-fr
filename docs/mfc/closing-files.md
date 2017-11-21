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
ms.openlocfilehash: 3833763394eda3ad64f1c72b80bee4d76785d5a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="closing-files"></a>Fermeture des fichiers
Comme d’habitude dans les opérations d’e/s, une fois que vous avez terminé avec un fichier, vous devez le fermer.  
  
#### <a name="to-close-a-file"></a>Pour fermer un fichier  
  
1.  Utilisez le **fermer** fonction membre. Cette fonction ferme le fichier de système de fichiers et vide les mémoires tampons si nécessaire.  
  
 Si vous avez alloué la [CFile](../mfc/reference/cfile-class.md) objet sur le frame (comme dans l’exemple illustré [ouverture de fichiers](../mfc/opening-files.md)), l’objet sera automatiquement être fermé et puis détruits lorsqu’il devient hors de portée. Notez que la suppression du `CFile` objet ne supprime pas le fichier physique du système de fichiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers](../mfc/files-in-mfc.md)

