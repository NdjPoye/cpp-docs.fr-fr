---
title: "Conteneurs de contrôles ActiveX : Utilisation de contrôles dans un conteneur de la boîte de dialogue Non | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c380d0a525c2f026054ebae1812450c4d4634c1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>Conteneurs de contrôles ActiveX : utilisation de contrôles dans un conteneur autre que de boîte de dialogue
Dans certaines applications, telles que SDI ou une application MDI, vous devez incorporer un contrôle dans une fenêtre de l’application. Le **créer** fonction membre de la classe wrapper, insérée par Visual C++, peut créer une instance du contrôle de manière dynamique, sans recourir à une boîte de dialogue.  
  
 Le **créer** fonction membre possède les paramètres suivants :  
  
 `lpszWindowName`  
 Pointeur vers le texte à afficher dans la propriété du contrôle Text ou Caption (le cas échéant).  
  
 `dwStyle`  
 Styles de Windows. Pour obtenir la liste complète, consultez [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol).  
  
 `rect`  
 Spécifie la taille et la position du contrôle.  
  
 `pParentWnd`  
 Spécifie la fenêtre du contrôle parent, généralement un `CDialog`. Il ne doit pas être **NULL**.  
  
 `nID`  
 Spécifie l’ID de contrôle et peut être utilisé par le conteneur pour faire référence au contrôle.  
  
 Un exemple d’utilisation de cette fonction pour créer dynamiquement un contrôle ActiveX serait dans une vue de formulaire d’une application SDI. Vous pouvez ensuite créer une instance du contrôle dans le `WM_CREATE` Gestionnaire de l’application.  
  
 Pour cet exemple, `CMyView` est la classe de vue principale, `CCirc` est la classe de wrapper et CIRC. H est l’en-tête (. H) du fichier de la classe wrapper.  
  
 Implémentation de cette fonctionnalité est un processus en quatre étapes.  
  
### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Pour créer dynamiquement un contrôle ActiveX dans une fenêtre de boîte de dialogue non  
  
1.  Insérez CIRC. H dans CMYVIEW. H, juste avant la `CMyView` définition de classe :  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  Ajouter une variable membre (de type `CCirc`) à la section protégée de la `CMyView` située dans CMYVIEW de définition de classe. H :  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  Ajouter un `WM_CREATE` le Gestionnaire de messages pour la classe `CMyView`.  
  
4.  Dans la fonction gestionnaire, `CMyView::OnCreate`, effectuez un appel à du contrôle `Create` à l’aide de la fonction le **cela** pointeur en tant que la fenêtre parente :  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  Regénérez le projet. Un contrôle Circ est créé dynamiquement chaque fois que la vue de l’application est créée.  
  
## <a name="see-also"></a>Voir aussi  
 [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)

