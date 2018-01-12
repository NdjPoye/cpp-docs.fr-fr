---
title: "Fichiers d’en-tête précompilés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdafx.h
dev_langs: C++
helpviewer_keywords:
- stdafx.h
- PCH files, file descriptions
- .pch files, file descriptions
- precompiled header files, file descriptions
- stdafx.cpp
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1208b000f57397764277cc0a43e223f7c781a06e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="precompiled-header-files"></a>Fichiers d'en-tête précompilés
Ces fichiers sont utilisés pour générer un fichier d’en-tête précompilé *Projname*.pch et un fichier de types précompilé Stdafx.obj.  
  
 Ces fichiers se trouvent dans le répertoire *Projname* . Dans l’Explorateur de solutions, Stdafx.h se trouve dans le dossier des fichiers d’en-tête, et Stdafx.cpp se trouve dans le dossier des fichiers sources.  
  
|Nom de fichier|Description|  
|---------------|-----------------|  
|stdafx.h|Fichier Include pour les fichiers Include système standard et pour les fichiers Include spécifiques au projet, qui sont fréquemment utilisés mais rarement modifiés.<br /><br /> Évitez de définir ou d’annuler la définition des macros _AFX_NO_XXX dans stdafx.h. Consultez l’article de la Base de connaissances sur PRB et l’apparition de problèmes après la définition de _AFX_NO_XXX. Vous pouvez trouver des articles de la Base de connaissances dans MSDN Library ou sur [http:// support.microsoft.com/](http://%20support.microsoft.com/).|  
|stdafx.cpp|Contient la directive de préprocesseur `#include "stdafx.h"` , et ajoute des fichiers Include pour les types précompilés. Les fichiers précompilés de tout type, notamment les fichiers d’en-tête, prennent en charge l’accélération des temps de compilation en limitant celle-ci aux fichiers qui en ont besoin. Une fois votre projet généré pour la première fois, vous remarquerez une accélération importante des temps de génération pour les builds suivantes, en raison de la présence de fichiers d’en-tête précompilés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)