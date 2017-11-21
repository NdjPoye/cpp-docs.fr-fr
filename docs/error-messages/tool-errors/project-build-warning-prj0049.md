---
title: "PRJ0049 d’avertissement de génération de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
helpviewer_keywords: PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6a8cd0a5a30f5ae3e7c2f551c667a014f8bb85f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-warning-prj0049"></a>Avertissement de génération de projet PRJ0049
Cible référencé '\<référence >' requiert .NET Framework \<MinFrameworkVersion > et ne pourra pas s’exécuter sur le framework cible de ce projet  
  
 Les applications créées à l’aide de Visual Studio 2008 peuvent spécifier la version de la [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] ils doivent cibler. Si vous ajoutez une référence à un assembly ou un projet qui dépend d’une version de la [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] qui est ultérieure à la version ciblée, vous obtenez cet avertissement au moment de la compilation.  
  
### <a name="to-correct-this-warning"></a>Pour corriger cet avertissement  
  
1.  Choisissez l'une des valeurs suivantes :  
  
    -   Modifiez le framework ciblé du projet de **Pages de propriétés** afin qu’il soit postérieure ou égale à la version de framework minimale de tous les assemblys référencés et les projets de boîte de dialogue. Pour plus d’informations, consultez [l’ajout de références](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Supprimez la référence à l’assembly ou le projet qui a une version de framework minimale ultérieure au framework ciblé. Ces éléments seront marqués avec une icône d’avertissement dans le fichier **Pages de propriétés**.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs et avertissements de génération de projet (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)