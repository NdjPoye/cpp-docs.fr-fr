---
title: "Création de nouvelles barres d’outils | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor, creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4315d101f194b9c0ff1a66b9e7cf81dc778cf372
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-new-toolbars"></a>Création de nouvelles barres d'outils
### <a name="to-create-a-new-toolbar"></a>Pour créer une nouvelle barre d’outils  
  
1.  Dans **ressource** afficher, cliquez sur votre fichier .rc, puis choisissez **ajouter une ressource** dans le menu contextuel. (Si vous avez une barre d’outils existante dans votre fichier .rc, vous pouvez simplement cliquer sur le **barre d’outils** et sélectionnez **insérer une barre d’outils** dans le menu contextuel.)  
  
     **Remarque** Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans le **ajouter une ressource** boîte de dialogue, sélectionnez **barre d’outils** dans les **Type de ressource** liste, puis cliquez sur **nouveau**.  
  
     Si un signe plus (+) s’affiche en regard du **barre d’outils** type de ressource, cela signifie que les modèles de la barre d’outils sont disponibles. Cliquez sur le signe plus pour développer la liste des modèles, sélectionnez un modèle, puis cliquez sur **nouveau**.  
  
     \- ou -  
  
3.  [Convertir une bitmap existante à une barre d’outils](../windows/converting-bitmaps-to-toolbars.md).  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Configuration requise  
  
 MFC ou ATL  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de barres d’outils](../windows/toolbar-editor.md)

