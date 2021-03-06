---
title: 'Icônes et curseurs : ressources Image pour les périphériques d’affichage (Éditeur d’images pour les icônes) | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- image resources, display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices, creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a977629cbae140afa1463a7765f193a7519e1f68
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons"></a>Icônes et des curseurs : ressources image pour les périphériques d'affichage (Éditeur d'images pour les icônes)
Les icônes et curseurs sont des ressources graphiques qui peuvent contenir plusieurs images de différentes tailles et modèles de couleurs pour différents types de périphériques d’affichage. De plus, un curseur a une « zone réactive », l’emplacement utilisé par Windows pour suivre sa position. Vous pouvez créer et modifier des icônes et des curseurs à l’aide de l’Éditeur d’images, comme les bitmaps et autres images.  
  
 Lorsque vous créez une icône ou un curseur, l’Éditeur d’images crée une image d’un type standard. Cette image est remplie initialement avec la couleur d’écran (transparente). Si l’image est un curseur, la zone réactive est initialement le coin supérieur gauche (coordonnées 0,0).  
  
 Par défaut, l’Éditeur d’images prend en charge la création d’images supplémentaires pour les périphériques répertoriés dans le tableau suivant. Vous pouvez créer des images pour d’autres périphériques en tapant les paramètres de hauteur, largeur et nombre de couleurs dans la boîte de dialogue [Image personnalisée](custom-image-dialog-box-image-editor-for-icons.md).  
  
> [!NOTE]
>  Grâce à l'Éditeur d'images, vous pouvez afficher des images 32 bits, mais vous ne pouvez pas les modifier.  
  
|Couleur|Largeur (pixels)|Hauteur (pixels)|  
|-----------|----------------------|-----------------------|  
|Monochrome|16|16|  
|Monochrome|32|32|  
|Monochrome|48|48|  
|Monochrome|64|64|  
|Monochrome|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [Création d’une image de périphérique (icône ou curseur)](../windows/creating-a-device-image-image-editor-for-icons.md)  
  
-   [Ajout d'une image pour un autre périphérique d'affichage](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [Copie d'une image de périphérique](../windows/copying-a-device-image-image-editor-for-icons.md)  
  
-   [Suppression d'une image de périphérique](../windows/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [Création de régions transparentes ou inversées dans des images de périphérique](../windows/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [Création d'une icône ou d'un curseur 256 couleurs](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [Définition de la zone réactive d'un curseur](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Spécifications  
 Aucun  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur d’images pour les icônes](../windows/image-editor-for-icons.md)   
 [icônes](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [Curseurs](http://msdn.microsoft.com/library/windows/desktop/ms646970)

