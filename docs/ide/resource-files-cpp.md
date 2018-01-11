---
title: Fichiers de ressources (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resource files
- resources [C++]
- file types [C++], resource files
ms.assetid: 338a4a0f-0c62-4ef1-a34f-5d86262d93a4
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 097ae6d1486292d7dcc62dd4191e16f57e6f0a3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-files-c"></a>Fichiers de ressources (C++)
Les ressources sont des éléments d’interface qui fournissent des informations à l’utilisateur. Bitmaps, icônes, barres d’outils et les curseurs sont toutes les ressources. Certaines ressources peuvent être manipulées pour exécuter une action, telle que sélectionner à partir d’un menu ou la saisie de données dans la boîte de dialogue.  
  
 Consultez [utilisation des ressources](../windows/working-with-resource-files.md) pour plus d’informations.  
  
|Nom de fichier|Emplacement du répertoire|Emplacement dans l'Explorateur de solutions|Description|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Nomproj*.rc|*Nomproj*|Fichiers sources|Le fichier de script de ressources pour le projet. Le fichier de script de ressources contient les éléments suivants, selon le type de projet et la prise en charge sélectionnée pour le projet (par exemple, les barres d’outils, les boîtes de dialogue ou HTML) :<br /><br /> -Définition du menu par défaut.<br />-Tables d’accélérateurs et chaîne.<br />-Par défaut **sur** boîte de dialogue.<br />-Les autres boîtes de dialogue.<br />-Fichier icône (res\\*NomProj*.ico).<br />-Informations de version.<br />-Les Bitmaps.<br />-Barre d’outils.<br />-Les fichiers HTML.<br /><br /> Le fichier de ressources inclut le fichier Afxres.rc pour les ressources standard de Microsoft Foundation Class.|  
|Resource.h|*Nomproj*|Fichiers d'en-tête|Le fichier d’en-tête de ressource qui contient les définitions pour les ressources utilisées par le projet.|  
|*Nomproj*.rc2|*Nomproj*\res|Fichiers sources|Le fichier de script contenant des ressources supplémentaires utilisés par le projet. Vous pouvez inclure le fichier .rc2 en haut du fichier .rc du projet.<br /><br /> Un fichier .rc2 est utile pour inclure des ressources utilisées par plusieurs projets différents. Au lieu de créer les mêmes ressources pour les projets différents, vous pouvez les placer dans un fichier .rc2 et ajouter le fichier .rc2 dans le fichier .rc principal.|  
|*Nomproj*.def|*Nomproj*|Fichiers sources|Le fichier de définition de module pour un projet DLL. Pour un contrôle, il fournit le nom et la description du contrôle, ainsi que la taille du tas de l’exécution.|  
|*Nomproj*.ico|*Nomproj*\res|Fichiers de ressources|Le fichier d’icône pour le projet ou le contrôle. Cette icône s’affiche lorsque l’application est réduite. Il est également utilisé dans l’application **sur** boîte. Par défaut, MFC fournit l’icône MFC et ATL fournit l’icône ATL.|  
|*Nomproj*Doc.ico|*Nomproj*\res|Fichiers de ressources|Le fichier d’icône pour un projet MFC qui prend en charge l’architecture document/vue.|  
|ToolBar.bmp|*Nomproj*\res|Fichiers de ressources|Le fichier bitmap représentant l’application ou le contrôle dans une barre d’outils ou une palette. Cette image bitmap est incluse dans le fichier de ressources du projet. La barre d’outils initiale et la barre d’état sont construites dans le **CMainFrame** classe.|  
|Ribbon.mfcribbon-ms|*Nomproj*\res|Fichiers de ressources|Le fichier de ressources qui contient le code XML qui définit les boutons, les contrôles et les attributs dans le ruban. Pour plus d'informations, consultez [Ribbon Designer (MFC)](../mfc/ribbon-designer-mfc.md).|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)