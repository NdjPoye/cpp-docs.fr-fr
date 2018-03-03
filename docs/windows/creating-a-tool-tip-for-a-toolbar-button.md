---
title: "Création d’une info-bulle pour un bouton de barre d’outils | Documents Microsoft"
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
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b5bb25a14d68c01c25d9242df89c1183511ca83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>Création d'une info-bulle pour un bouton de barre d'outils
### <a name="to-create-a-tool-tip"></a>Pour créer une info-bulle  
  
1.  Sélectionnez le bouton de barre d’outils.  
  
2.  Dans le [fenêtre Propriétés](/visualstudio/ide/reference/properties-window), dans le **invite** champ de propriété, ajoutez une description du bouton de la barre d’état ; après le message, ajoutez \n et l’info-bulle nom.  
  
 Un exemple courant d’une info-bulle est le bouton Imprimer dans WordPad :  
  
 1. Ouvrez WordPad.  
  
 2. Placez le pointeur de la souris sur le **impression** bouton de barre d’outils.  
  
 3. Notez que le mot « Imprimer » s’affiche sous le pointeur de la souris.  
  
 4. Examinez la barre d’état (en bas de la fenêtre WordPad), notez le texte « Imprime le document actif » s’affiche.  
  
 L’impression à l’étape 3 est « info-bulle nom » et le « imprime le document actif » à partir de l’étape 4 est la « description du bouton de la barre d’état ».  
  
 Si vous souhaitez que cet effet à l’aide de la **barre d’outils** éditeur, vous définissez la **invite** propriété **imprime le document actif\nImprimer**.  
  
> [!NOTE]
>  Vous pouvez modifier le texte d’invite à l’aide de la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window).  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Configuration requise  
  
 MFC ou ATL  
  
## <a name="see-also"></a>Voir aussi  
 [Création, déplacement et modification de boutons de barre d’outils](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Éditeur de barres d’outils](../windows/toolbar-editor.md)

