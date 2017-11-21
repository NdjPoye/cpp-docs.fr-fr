---
title: "Création d’une info-bulle pour un bouton de barre d’outils | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e9399341f19a614783c0f8f873051ed048d89b35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](https://msdn.microsoft.com/library/f45fce5x.aspx) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](https://msdn.microsoft.com/library/xbx3z216.aspx). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Spécifications  
  
 MFC ou ATL  
  
## <a name="see-also"></a>Voir aussi  
 [Création, déplacement et modification de boutons de barre d’outils](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Éditeur de barres d’outils](../windows/toolbar-editor.md)

