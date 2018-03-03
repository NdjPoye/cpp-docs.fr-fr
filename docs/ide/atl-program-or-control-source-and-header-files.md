---
title: "Fichiers d’en-tête et sources de contrôle ou de programme ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a13a4c6ddb74a6f63b5da1171a3d4360199b508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-program-or-control-source-and-header-files"></a>Fichiers d'en-tête et fichiers sources de contrôle ou de programme ATL
Les fichiers suivants sont créés lorsque vous créez un projet ATL dans Visual Studio, selon les options que vous sélectionnez pour le projet que vous créez.  
  
 Tous ces fichiers se trouvent dans le *NomProj* directory et dans le dossier de fichiers d’en-tête (fichiers .h) ou le dossier des fichiers de code Source (fichiers .cpp) dans l’Explorateur de solutions.  
  
|Nom de fichier|Description|  
|---------------|-----------------|  
|*Nomproj*.h|Le fichier include principal qui contient les définitions d’interface C++ et les déclarations de GUID des éléments définis dans ATLSample.idl. Il est régénéré par MIDL pendant la compilation.|  
|*Nomproj*.cpp|Le fichier source du programme principal. Il contient l’implémentation de vos exportations de DLL pour un serveur in-process et l’implémentation de `WinMain` pour un serveur local. Pour un service, il implémente en outre toutes les fonctions de gestion de service.|  
|Resource.h|Le fichier d’en-tête pour le fichier de ressources.|  
|StdAfx.cpp|Inclut les fichiers StdAfx.h et Atlimpl.cpp.|  
|StdAfx.h|Inclut les fichiers d’en-tête ATL.|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Fichiers d’en-tête et sources de contrôle ou de programme MFC](../ide/mfc-program-or-control-source-and-header-files.md)   
 [Projets CLR](../ide/files-created-for-clr-projects.md)