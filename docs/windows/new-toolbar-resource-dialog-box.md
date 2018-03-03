---
title: "Nouvelle ressource de barre d’outils, boîte de dialogue | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.newtoolbarresource
dev_langs:
- C++
helpviewer_keywords:
- New Toolbar Resource dialog box
ms.assetid: 52dd01ad-e748-4ab2-b3eb-59f5df990ca6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c30301b8887013d72e7ae2ab2d70650de7d7f0e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="new-toolbar-resource-dialog-box"></a>Nouvelle ressource de barre d'outils (boîte de dialogue)
La boîte de dialogue Nouvelle ressource de barre d’outils vous permet de spécifier la largeur et la hauteur des boutons que vous ajoutez à une ressource de barre d’outils. La valeur par défaut est 16 x 15 pixels.  
  
 Une image bitmap qui est utilisée pour créer une barre d’outils a une largeur maximale de 2048. Par conséquent, si vous définissez la **largeur du bouton** à 512, vous ne pouvez avoir quatre boutons. Si vous définissez la largeur à 513, vous pouvez avoir uniquement trois boutons.  
  
 **Largeur du bouton**  
 Offre un espace vous permettant d’entrer la largeur pour les boutons de barre d’outils que vous convertissez une ressource bitmap à une ressource de barre d’outils. Les images sont rognées à la largeur et la hauteur spécifiées et les couleurs sont ajustées pour utiliser les couleurs de barre d’outils standard (16 couleurs).  
  
 **Hauteur du bouton**  
 Offre un espace vous permettant d’entrer la hauteur pour les boutons de barre d’outils que vous convertissez une ressource bitmap à une ressource de barre d’outils. Les images sont rognées à la largeur et la hauteur spécifiées et les couleurs sont ajustées pour utiliser les couleurs de barre d’outils standard (16 couleurs).  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Configuration requise  
 MFC ou ATL  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés de bouton de barre d’outils](../windows/toolbar-button-properties.md)   
 [Conversion de Bitmaps en barres d’outils](../windows/converting-bitmaps-to-toolbars.md)   
 [Éditeur de barres d’outils](../windows/toolbar-editor.md)

