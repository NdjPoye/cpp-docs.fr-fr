---
title: "Accès de type sécurisé aux contrôles sans Assistants Code | Documents Microsoft"
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
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5a4adce63851620326add61857433b32e1fad5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Accès de type sécurisé aux contrôles sans Assistants Code
La première approche pour la création d’accès de type sécurisé aux contrôles utilise une fonction membre inline pour effectuer un cast de type de retour de la classe `CWnd`de `GetDlgItem` fonction membre vers le type de contrôle C++ approprié, comme dans cet exemple :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 Vous pouvez ensuite utiliser cette fonction membre pour accéder au contrôle de manière sécurisée avec un code similaire à ce qui suit :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Accès de type sécurisé aux contrôles dans une boîte de dialogue](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Accès de type sécurisé aux contrôles avec Assistants Code](../mfc/type-safe-access-to-controls-with-code-wizards.md)

