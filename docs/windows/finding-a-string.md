---
title: "Recherche d’une chaîne | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a66b5dd34aa21a2a0791ecbc71bfd4abcc90c4fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="finding-a-string"></a>Recherche d'une chaîne
Vous pouvez rechercher une ou plusieurs chaînes dans la table de chaînes et utiliser [des expressions régulières](/visualstudio/ide/using-regular-expressions-in-visual-studio) avec la **rechercher dans les fichiers** commande (**modifier** menu) pour rechercher toutes les instances de chaînes qui correspondent à un modèle.  
  
### <a name="to-find-a-string-in-the-string-table"></a>Pour rechercher une chaîne dans la table de chaînes  
  
1.  Ouvrez la table de chaînes en double-cliquant sur son icône dans [affichage des ressources](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Si votre projet ne contient pas déjà un fichier .rc, consultez [Création d'un fichier de script de ressources](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Sur le **modifier** menu, cliquez sur **rechercher et remplacer**, puis choisissez **trouver**.  
  
3.  Dans le **rechercher** zone, sélectionnez une chaîne de recherche antérieure dans la liste déroulante ou tapez l’identificateur de texte ou de ressource de légende de la chaîne à rechercher.  
  
4.  Sélectionnez un de le **trouver** options.  
  
5.  Cliquez sur **suivant**.  
  
    > [!TIP]
    >  Pour utiliser des expressions régulières lors de la recherche de fichiers, utilisez le **rechercher dans les fichiers** commande. Tapez une expression régulière pour mettre en correspondance un modèle ou cliquez sur le bouton à droite de la **rechercher** à cocher pour afficher une liste d’expressions régulières de recherche. Lorsque vous sélectionnez une expression dans cette liste, elle se substitue au texte de recherche dans les **rechercher** boîte. Si vous utilisez des expressions régulières, assurez-vous que le **utiliser : Expressions régulières** case à cocher est activée.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés (ceux qui ciblent le common language runtime), consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour obtenir des informations sur l’ajout de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, et ceci manuellement, consultez [Procédure pas à pas : localisation des applications Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) et [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **Spécifications**  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de chaînes](../windows/string-editor.md)   

