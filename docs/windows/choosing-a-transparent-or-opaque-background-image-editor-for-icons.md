---
title: "Choix d’un arrière-plan Transparent ou Opaque (Éditeur d’images pour les icônes) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- opaque backgrounds
- background colors, images
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- background images
- images [C++], transparency
- images [C++], opaque background
- transparent backgrounds
- transparency, background
- transparent backgrounds, images
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea4c5ae14bdf11583a3aba21dfd90e0a6f2fd92a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Choix d'un arrière-plan transparent ou opaque (Éditeur d'images pour les icônes)
Lorsque vous déplacez ou copiez une sélection à partir d’une image, les pixels de la sélection qui correspondent à la couleur d’arrière-plan actuelle sont, par défaut, transparent ; ils ne masquent pas pixels dans l’emplacement cible.  
  
 Vous pouvez passer d’un arrière-plan transparent (la valeur par défaut) à un arrière-plan opaque et vice versa. Lorsque vous utilisez un outil de sélection, le **arrière-plan Transparent** et **arrière-plan Opaque** options s’affichent dans le sélecteur d’options sur la **Éditeur d’images** barre d’outils (comme indiqué ci-dessous).  
  
 ![Options d’arrière-plan &#45; opaque ou transparent](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
Options transparentes et opaques sur la barre d’outils Éditeur d’images  
  
### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Pour basculer entre un arrière-plan transparent et opaque  
  
1.  Dans le **Éditeur d’images** barre d’outils, cliquez sur le **Option** sélecteur, puis cliquez sur l’arrière-plan approprié :  
  
    -   **Arrière-plan opaque (O)**: image existante est obscurcie par toutes les parties de la sélection.  
  
    -   **Arrière-plan transparent (T)**: illustration existant par le biais de la sélection, les éléments qui correspondent à la couleur d’arrière-plan actuelle.  
  
 \- ou -  
  
-   Sur le **Image** menu, activez ou désactivez **dessiner Opaque**.  
  
 Vous pouvez modifier la couleur d’arrière-plan alors qu’une sélection est déjà en vigueur pour modifier les parties de l’image sont transparents.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](https://msdn.microsoft.com/library/f45fce5x.aspx) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](https://msdn.microsoft.com/library/xbx3z216.aspx). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Spécifications  
  
 Aucune  
  
## <a name="see-also"></a>Voir aussi  
 [Touches accélérateur](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Utilisation des couleurs](../windows/working-with-color-image-editor-for-icons.md)