---
title: "Aperçu des ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0eca56e607c916e28afc7bf513d853bcf6d94b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="previewing-resources"></a>Aperçu des ressources
L’aperçu des ressources permet d’afficher des ressources graphiques sans les ouvrir. L’aperçu est également utile pour les fichiers exécutables une fois que vous avez compilé, car les identificateurs de ressource se transformer en nombres. Étant donné que ces identificateurs numériques ne fournissent pas suffisamment d’informations, l’aperçu des ressources vous permet de les identifier rapidement.  
  
 Vous pouvez afficher un aperçu de la présentation visuelle des types de ressources suivants :  
  
-   Bitmap  
  
-   Boîte de dialogue  
  
-   Icône  
  
-   Menu  
  
-   Curseur  
  
-   ToolBar  
  
 La fonction d’aperçu visuel ne s’applique pas aux ressources de l’accélérateur, manifeste, Table de chaînes et les informations de Version.  
  
### <a name="to-preview-resources"></a>Pour afficher un aperçu des ressources  
  
1.  Dans [affichage des ressources](../windows/resource-view-window.md) ou une fenêtre de document, sélectionnez votre ressource, par exemple, IDD_ABOUTBOX.  
  
     **Remarque** Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Dans le [fenêtre Propriétés](/visualstudio/ide/reference/properties-window), cliquez sur le **Pages de propriétés** bouton.  
  
     \- ou -  
  
3.  Sur le **vue** menu, cliquez sur **Pages de propriétés**.  
  
     La Page de propriétés pour la ressource s’ouvre, affichant un aperçu de la ressource. Vous pouvez ensuite utiliser l’et touches de direction pour naviguer dans le contrôle d’arborescence dans l’affichage des ressources ou la fenêtre de document. La Page de propriétés reste ouverte et affiche toutes les ressources qui a le focus et sont en mesure d’afficher un aperçu.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Spécifications**  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : ouvrir un fichier de Script de ressources en dehors d’un projet (autonome)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Éditeurs de ressources](../windows/resource-editors.md)

