---
title: Fichiers d’en-tête et sources de contrôle ou de programme ATL | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e8e5065cebab002e9c48aef560eb9f2feab67e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
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