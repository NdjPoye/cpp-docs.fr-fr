---
title: "Fichiers d&#39;en-t&#234;te pr&#233;compil&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""stdafx.h""
  - "stdafx.h"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stdafx.h"
  - "fichiers PCH, descriptions de fichier"
  - "fichiers .pch, descriptions de fichier"
  - "fichiers d’en-tête précompilés, descriptions de fichier"
  - "stdafx.cpp"
ms.assetid: 8228d87a-5609-41f3-9697-b16094c000e5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Fichiers d&#39;en-t&#234;te pr&#233;compil&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces fichiers sont utilisés pour générer un fichier d’en\-tête précompilé *Projname*.pch et un fichier de types précompilé Stdafx.obj.  
  
 Ces fichiers se trouvent dans le répertoire *Projname*. Dans l’Explorateur de solutions, Stdafx.h se trouve dans le dossier des fichiers d’en\-tête, et Stdafx.cpp se trouve dans le dossier des fichiers sources.  
  
|Nom de fichier|Description|  
|--------------------|-----------------|  
|Stdafx.h|Fichier Include pour les fichiers Include système standard et pour les fichiers Include spécifiques au projet, qui sont fréquemment utilisés mais rarement modifiés.<br /><br /> Évitez de définir ou d’annuler la définition des macros \_AFX\_NO\_XXX dans stdafx.h. Consultez l’article de la Base de connaissances sur PRB et l’apparition de problèmes après la définition de \_AFX\_NO\_XXX. Vous pouvez trouver des articles de la Base de connaissances dans MSDN Library ou sur [http:\/\/ support.microsoft.com\/](http://%20support.microsoft.com/).|  
|Stdafx.cpp|Contient la directive de préprocesseur `#include "stdafx.h"`, et ajoute des fichiers Include pour les types précompilés. Les fichiers précompilés de tout type, notamment les fichiers d’en\-tête, prennent en charge l’accélération des temps de compilation en limitant celle\-ci aux fichiers qui en ont besoin. Une fois votre projet généré pour la première fois, vous remarquerez une accélération importante des temps de génération pour les builds suivantes, en raison de la présence de fichiers d’en\-tête précompilés.|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Comment : spécifier des propriétés de projet avec des pages de propriétés](../misc/how-to-specify-project-properties-with-property-pages.md)