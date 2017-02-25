---
title: "Fichiers d&#39;en-t&#234;te et fichiers sources de contr&#244;le ou de programme ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "types de fichiers (C++), source et en-têtes ATL"
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Fichiers d&#39;en-t&#234;te et fichiers sources de contr&#244;le ou de programme ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez un projet ATL dans Visual Studio, les fichiers suivants sont également créés en fonction des options sélectionnées pour votre nouveau projet.  
  
 Tous ces fichiers sont stockés dans le répertoire *Nomprojet* et figurent soit dans le dossier Header Files \(fichiers .h\), soit dans le dossier Source Files \(fichiers .cpp\) de l'Explorateur de solutions.  
  
|Nom du fichier|Description|  
|--------------------|-----------------|  
|*Nomprojet*.h|Le fichier Include principal qui contient les définitions d'interface de C\+\+ et déclarations GUID des éléments définis dans ATLSample.idl.  Il est régénéré par MIDL pendant la compilation.|  
|*Nomprojet*.cpp|Fichier source principal de programme.  Il contient l'implémentation de vos exportations de DLL pour un serveur in\-process et l'implémentation de `WinMain` pour un serveur local.  Dans le cas d'un service, ce fichier implémente en plus toutes les fonctions de gestion du service.|  
|Resource.h|Fichier d'en\-tête pour le fichier de ressources.|  
|StdAfx.cpp|Contient les fichiers StdAfx.h et Atlimpl.cpp.|  
|StdAfx.h|Contient les fichiers d'en\-tête ATL.|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Fichiers d'en\-tête et fichiers sources de contrôle ou de programme MFC](../ide/mfc-program-or-control-source-and-header-files.md)   
 [Projets CLR](../ide/files-created-for-clr-projects.md)