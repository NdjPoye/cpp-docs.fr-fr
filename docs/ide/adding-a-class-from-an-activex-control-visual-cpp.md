---
title: "Ajout d’une classe à partir d’un contrôle ActiveX (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f059396c91ddb51247347d10e6c8f79a6c95522f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>Ajout d'une classe à partir d'un contrôle ActiveX (Visual C++)
Utilisez cet Assistant pour créer une classe MFC à partir d’une interface dans un contrôle ActiveX disponible. Vous pouvez ajouter une classe MFC à une [application MFC](../mfc/reference/creating-an-mfc-application.md), un [DLL MFC](../mfc/reference/creating-an-mfc-dll-project.md), ou un [contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Vous n’avez pas besoin de créer un projet MFC avec Automation activé pour ajouter une classe à partir d’un contrôle ActiveX.  
  
 Un contrôle ActiveX est un composant logiciel réutilisable basé sur le modèle COM (Component Object) qui prend en charge un large éventail de fonctionnalités OLE et peut être personnalisé pour s’ajuster à nombreux besoins logiciels. Contrôles ActiveX sont conçus pour une utilisation dans des conteneurs de contrôles ActiveX ordinaires et sur Internet dans les pages du World Wide Web.  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>Pour ajouter une classe MFC à partir d’un contrôle ActiveX  
  
1.  Dans le **l’Explorateur de solutions** ou [affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez sur le nom du projet auquel vous souhaitez ajouter la classe du contrôle ActiveX.  
  
2.  Dans le menu contextuel, cliquez sur **ajouter**, puis cliquez sur **ajouter une classe**.  
  
3.  Dans le [ajouter une classe](../ide/add-class-dialog-box.md) boîte de dialogue, dans le volet Modèles, cliquez sur **classe MFC à partir du contrôle ActiveX**, puis cliquez sur **ouvrir** pour afficher le [ajouter une classe à partir d’ActiveX Contrôle Assistant](../ide/add-class-from-activex-control-wizard.md).  
  
 Dans l’Assistant, vous pouvez ajouter plus d’une interface dans un contrôle ActiveX. De même, vous pouvez créer des classes à partir de plusieurs contrôles ActiveX dans une session d’Assistant unique.  
  
 Vous pouvez ajouter des classes de contrôles ActiveX inscrits dans votre système, ou vous pouvez ajouter des classes à partir de contrôles ActiveX situés dans les fichiers de bibliothèque de types (.tlb, .olb, .dll, .ocx ou .exe) sans préalable par leur inscription dans votre système. Consultez [Registering OLE Controls](../mfc/reference/registering-ole-controls.md) pour plus d’informations sur l’inscription des contrôles ActiveX.  
  
 L’Assistant crée une classe MFC, dérivée de [CWnd](../mfc/reference/cwnd-class.md) ou à partir de [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), pour chaque interface que vous ajoutez à partir du contrôle ActiveX sélectionné.  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Introduction à COM et ATL](../atl/introduction-to-com-and-atl.md)