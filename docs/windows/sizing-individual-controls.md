---
title: "Dimensionnement de contrôles individuels | Documents Microsoft"
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
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b019cd2bbf68a4321bafd6dd960ffbcdba2dddf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sizing-individual-controls"></a>Dimensionnement de contrôles individuels
Utilisez les poignées de redimensionnement pour redimensionner un contrôle. Lorsque le pointeur est placé sur une poignée de dimensionnement, il change de forme pour indiquer les sens dans lequel le contrôle peut être redimensionné. Poignées de dimensionnement actives sont pleines ; Si une poignée de redimensionnement est vide, le contrôle ne peut pas être redimensionné le long de cet axe.  
  
 Vous pouvez également modifier la taille d’un contrôle par l’alignement du contrôle aux repères ou les marges, ou en déplaçant un aligné contrôle et guide en dehors d’un autre.  
  
### <a name="to-size-a-control"></a>Pour dimensionner un contrôle  
  
1.  Sélectionnez le contrôle.  
  
2.  Faites glisser les poignées de redimensionnement pour modifier la taille du contrôle :  
  
    -   Poignées de redimensionnement en haut et côtés modifier la taille horizontale ou verticale.  
  
    -   Poignées de redimensionnement dans les angles modifier la taille horizontale et verticale.  
  
    > [!TIP]
    >  Vous pouvez redimensionner le contrôle d’unité une boîte de dialogue (DLU) à la fois en maintenant la touche MAJ enfoncée et en utilisant les touches droite et bas.  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Pour ajuster automatiquement un contrôle pour s’adapter au texte qu’il contient  
  
1.  Choisissez **ajuster au contenu** à partir de la **Format** menu.  
  
 \- ou -  
  
-   Cliquez sur le contrôle et choisissez **ajuster au contenu** dans le menu contextuel.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Configuration requise  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles dans les boîtes de dialogue](../windows/controls-in-dialog-boxes.md)   
 [Contrôles](../mfc/controls-mfc.md)

