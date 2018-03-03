---
title: "Création d’un pinceau personnalisé (Éditeur d’images pour les icônes) | Documents Microsoft"
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
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38f376053635708372c09a37aa0810e4305db60a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Création d'un pinceau personnalisé (Éditeur d'images pour les icônes)
Un pinceau personnalisé est une partie rectangulaire d’une image que vous sélectionnez et utilisez comme l’une des formes prêtes à l’emploi de l’éditeur d’images. Toutes les opérations que vous pouvez effectuer sur une sélection, vous pouvez effectuer sur un pinceau personnalisé.  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Pour créer un pinceau personnalisé à partir d’une partie d’une image  
  
1.  [Sélectionnez la partie de l’image](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) que vous souhaitez utiliser comme pinceau.  
  
2.  Contenant le **MAJ** clé vers le bas, cliquez sur la sélection et faites-la glisser sur l’image.  
  
     \- ou -  
  
3.  À partir de la **Image** menu, choisissez **utiliser la sélection comme pinceau**.  
  
     Votre sélection devient un pinceau personnalisé qui distribue les couleurs dans la sélection sur l’image. Copies de la sélection sont laissées sur le chemin de déplacement. Vous faites glisser plus lentement, le nombre de copies est effectuées.  
  
     **Remarque** en cliquant sur le **utiliser une sélection comme pinceau** sans tout d’abord sélectionner une partie de l’image utilise l’image entière comme un pinceau. Le résultat de l’utilisation d’un pinceau personnalisé varient également selon que vous avez sélectionné un [arrière-plan Transparent ou Opaque](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 Pixels d’un pinceau personnalisé qui correspondent à la couleur d’arrière-plan actuelle sont transparents : ils dessinera pas sur l’image existante. Vous pouvez modifier ce comportement afin que les pixels de la couleur d’arrière-plan peindre l’image existante.  
  
 Vous pouvez utiliser le pinceau personnalisé comme un tampon ou un stencil pour créer différents effets spéciaux.  
  
#### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Pour dessiner des formes de pinceau personnalisé dans la couleur d’arrière-plan  
  
1.  [Sélectionnez un arrière-plan transparent ou opaque](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
2.  [Définir la couleur d’arrière-plan](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) à la couleur dans laquelle vous souhaitez dessiner.  
  
3.  Placez le pinceau personnalisé où vous souhaitez dessiner.  
  
4.  Cliquez sur le bouton droit de la souris. Les zones opaques du pinceau personnalisé sont dessinées dans la couleur d’arrière-plan.  
  
#### <a name="to-double-or-halve-the-custom-brush-size"></a>Double-cliquez ou réduire de moitié la taille du pinceau personnalisé  
  
1.  Appuyez sur la **signe** (**+**) pour doubler la taille du pinceau, ou le **signe** (**-**) clé à diviser en deux .  
  
#### <a name="to-cancel-the-custom-brush"></a>Pour annuler un pinceau personnalisé  
  
1.  Appuyez sur **ÉCHAP** ou choisissez un autre outil de dessin.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Spécifications  
 Aucun  
  
## <a name="see-also"></a>Voir aussi  
 [Touches accélérateur](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Modification de ressources graphiques](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Éditeur d’images pour les icônes](../windows/image-editor-for-icons.md)

