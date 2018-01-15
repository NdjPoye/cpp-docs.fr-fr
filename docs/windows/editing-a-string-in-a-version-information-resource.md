---
title: "Modification d’une chaîne dans une ressource d’informations de Version | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.version
dev_langs: C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5add7bfb11b1c416853bb10ddbb2956885e181ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="editing-a-string-in-a-version-information-resource"></a>Modification d'une chaîne dans une ressource d'informations sur la version
### <a name="to-edit-a-string-in-a-version-information-resource"></a>Pour modifier une chaîne dans une ressource d’informations sur la version  
  
1.  Cliquez sur l’élément pour le sélectionner, puis recliquez dessus pour commencer à le modifier. Apportez les modifications directement dans la table d’informations sur la version ou dans la fenêtre [Propriétés](/visualstudio/ide/reference/properties-window). Les modifications que vous apportez apparaîtront aux deux emplacements.  
  
     **Remarque** Lors de la modification de la clé **FILEFLAGS** dans l’Éditeur d’informations sur la version, vous remarquerez que vous ne pouvez pas définir les propriétés **Debug**, **Private Build**ou **Special Build** (dans la fenêtre Propriétés) pour les fichiers .rc :  
  
    -   L’Éditeur d’informations sur la version définit la propriété **Debug** avec un #ifdef dans le script de ressources, en fonction de l’indicateur de build **_DEBUG** .  
  
    -   Si la clé **Private Build** a une **Valeur** définie dans la table d’informations sur la version, la propriété **Private Build** correspondante (dans la fenêtre Propriétés) de la clé **FILEFLAGS** a la valeur **True**. Si la **Valeur** est vide, la propriété est **False**. De même, la clé **Special Build** (dans la table d’informations sur la version) est liée à la propriété **Special Build** de la clé **FILEFLAGS** .  
  
 Vous pouvez trier la séquence d’informations du bloc de chaîne en cliquant sur l’en-tête de colonne Clé ou Valeur. Ces en-têtes réorganisent automatiquement les informations dans la séquence sélectionnée.  
  
 Pour plus d’informations sur l’ajout de ressources aux projets managés, consultez [ressources dans les applications de bureau](/dotnet/framework/resources/index) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel des fichiers de ressources aux projets managés, l’accès aux ressources, affichage de ressources statiques et l’assignation de chaînes de ressources aux propriétés, consultez [création de fichiers de ressources pour les applications de bureau](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Pour plus d’informations sur la globalisation et localisation des ressources dans les applications managées, consultez [globalisation et localisation d’Applications .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 **Spécifications**  
  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur d’informations de version](../windows/version-information-editor.md)   
 [Informations de version (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

