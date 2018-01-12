---
title: "Fichiers créés pour les projets CLR | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4abf5415e9b252a7cc92408fb273d226106fc16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="files-created-for-clr-projects"></a>Fichiers créés pour les projets CLR
Lorsque vous utilisez des modèles Visual C++ pour créer vos projets, plusieurs fichiers sont créés, en fonction du modèle que vous utilisez. Le tableau suivant répertorie tous les fichiers qui sont créés par les modèles de projet pour les projets .NET Framework.  
  
|Nom de fichier|Description du fichier|  
|---------------|----------------------|  
|AssemblyInfo.cpp|Le fichier qui contient des informations (attributs, fichiers, ressources, types, informations de contrôle de version, les informations de signature, etc.) pour modifier les métadonnées d’assembly du projet. Pour plus d’informations, consultez [contenu d’un Assembly](/dotnet/framework/app-domains/assembly-contents).|  
|*nomproj*.asmx|Un fichier texte que références les classes managées qui encapsulent la fonctionnalité du service Web XML.|  
|*nomproj*.cpp|Le principal fichier source et point d’entrée dans l’application que Visual Studio créé pour vous. Identifie le fichier .dll du projet et l’espace de noms du projet. Fournissez votre propre code dans ce fichier.|  
|*nomproj*.vsdisco|Un fichier de déploiement XML contenant des liens vers d’autres ressources qui décrivent le service Web XML.|  
|*nomproj*.h|Le principal fichier include pour le projet qui contient l’ensemble des déclarations, symboles globaux, et `#include` des directives pour les autres fichiers d’en-tête.|  
|*nomproj*.sln|Le fichier de solution permettant d’organiser tous les éléments de votre projet dans une solution unique au sein de l’environnement de développement.|  
|*nomproj*.suo|Le fichier d’options de solution utilisé dans l’environnement de développement.|  
|*nomproj*.vcxproj|Le fichier projet est utilisé dans l’environnement de développement qui stocke les informations spécifiques à ce projet.|  
|ReadMe.txt|Un fichier qui décrit chaque fichier dans votre projet à l’aide de noms de fichiers réels créés par le modèle.|