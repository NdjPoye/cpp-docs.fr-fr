---
title: "L’enregistrement et chargement de différentes Palettes (Éditeur d’images pour les icônes) de couleurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7ef7200300eb4809496bfa342e9bab645f4c40e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Enregistrement et chargement de différentes palettes de couleurs (Éditeur d'images pour les icônes)
Vous pouvez enregistrer et charger une palette de couleurs contienne [personnalisé couleurs](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (Par défaut, la palette de couleurs utilisée en dernier est automatiquement chargée quand vous démarrez Visual Studio.)  
  
> [!TIP]
>  Dans la mesure où l'éditeur d'images n'a aucun moyen de rétablir la palette de couleurs par défaut, vous devez enregistrer la palette de couleurs par défaut sous un nom tel que standard.pal ou defaut.pal pour pouvoir restaurer facilement les paramètres par défaut.  
  
### <a name="to-save-a-custom-colors-palette"></a>Pour enregistrer une palette de couleurs personnalisées  
  
1.  À partir de la **Image** menu, choisissez **enregistrer la Palette**.  
  
2.  Accédez au répertoire où vous souhaitez enregistrer la palette, puis tapez le nom de cette dernière.  
  
3.  Cliquez sur **Enregistrer**.  
  
### <a name="to-load-a-custom-colors-palette"></a>Pour charger une palette de couleurs personnalisées  
  
1.  À partir de la **Image** menu, choisissez **charger la Palette**.  
  
2.  Dans le [boîte de dialogue Charger la Palette de couleurs](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), accédez au répertoire approprié et sélectionnez la palette à charger. Les palettes de couleurs sont enregistrées avec une extension de fichier .pal.  
  

  
 Configuration requise  
  
 Aucun.  
  
## <a name="see-also"></a>Voir aussi  
 [Touches accélérateur](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Utilisation des couleurs](../windows/working-with-color-image-editor-for-icons.md)