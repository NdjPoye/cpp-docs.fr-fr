---
title: "Conteneurs de contrôles ActiveX : Insertion d’un contrôle dans une Application de conteneur du contrôle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a1eaaf0426726f252fc4990f06faa73b0598cfbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>Conteneurs de contrôles ActiveX : insertion d'un contrôle dans une application de conteneur de contrôle
Avant de pouvoir accéder à un contrôle ActiveX à partir d’une application de conteneur de contrôle ActiveX, vous devez ajouter le contrôle ActiveX à l’application de conteneur à l’aide de la [insérer un contrôle ActiveX](../windows/insert-activex-control-dialog-box.md) boîte de dialogue.  
  
 Pour ajouter un contrôle ActiveX au projet conteneur de contrôle ActiveX, consultez [affichage et ajout de contrôles ActiveX à une boîte de dialogue](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Une fois que vous ajoutez le contrôle, vous devez ajouter une variable membre (du type de contrôle ActiveX) à la classe de boîte de dialogue. Pour plus d’informations sur cette procédure, consultez [Ajout d’une Variable membre](../ide/adding-a-member-variable-visual-cpp.md).  
  
 Une fois que vous avez ajouté la variable membre à une classe, appelée une classe wrapper, est automatiquement générée et ajoutée à votre projet. Cette classe est utilisée en tant qu’interface entre le conteneur de contrôle et le contrôle incorporé.  
  
## <a name="see-also"></a>Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)

