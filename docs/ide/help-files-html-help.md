---
title: Aide (aide HTML) de fichiers | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d180fe4f9cf1baf26b27423ffda975bfe0fe85ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="help-files-html-help"></a>Fichiers d'aide (aide HTML)
Les fichiers suivants sont créés lorsque vous ajoutez la prise en charge de l’aide de type HTML à votre application en sélectionnant le **contextuelle** case à cocher, puis en sélectionnant **format d’aide HTML** dans les [Fonctionnalités avancées](../mfc/reference/advanced-features-mfc-application-wizard.md) page de l’Assistant Application MFC.  
  
|Nom de fichier|Emplacement du répertoire|Emplacement dans l'Explorateur de solutions|Description|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Nomproj*.hhp|*Nomproj*\hlp|fichiers d'aide HTML|Le fichier projet d’aide. Il contient les données nécessaires à la compilation des fichiers d’aide en un fichier .hxs ou .chm.|  
|*Nomproj*.hhk|*Nomproj*\hlp|fichiers d'aide HTML|Contient un index des rubriques d’aide.|  
|*Nomproj*.hhc|*Nomproj*\hlp|fichiers d'aide HTML|Le contenu du projet d’aide.|  
|Makehtmlhelp.bat|*Nomproj*|Fichiers sources|Utilisé par le système pour générer le projet d’aide lors de la compilation du projet.|  
|Afxcore.htm|*Nomproj*\hlp|Rubriques d’aide HTML|Contient les rubriques d’aide standards pour les commandes MFC standard et les objets de l’écran. Ajouter vos propres rubriques d’aide à ce fichier.|  
|Afxprint.htm|*Nomproj*\hlp|Rubriques d’aide HTML|Contient les rubriques d’aide pour les commandes d’impression.|  
|*.jpg ; \*.gif|*Nomproj*\hlp\Images|Fichiers de ressources|Contenir des images pour les rubriques d’aide générées différents.|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)