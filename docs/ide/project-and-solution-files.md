---
title: Fichiers projet et Solution | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.files.projectandsolution
dev_langs:
- C++
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08cf1386ef177823c37bc285392309ec47f3c464
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="project-and-solution-files"></a>Fichiers projet et solution
Les fichiers suivants sont créés en même temps que vous créez un projet dans Visual Studio. Ils servent à gérer les fichiers projet de la solution.  
  
|Nom de fichier|Emplacement du répertoire|Emplacement dans l'Explorateur de solutions|Description|  
|--------------|------------------------|--------------------------------|-----------------|  
|*Nomsol*.sln|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *solution* fichier. Permet d'organiser tous les éléments d'un ou plusieurs projets dans une même solution.|  
|*Nomproj*.suo|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *options de solution* fichier. Permet de stocker les personnalisations de la solution pour que chaque fois que vous ouvrez un projet ou un fichier de la solution, il ait l'apparence et le comportement que vous attendez.|  
|*Nomproj*.vcxproj|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *projet* fichier. Permet de stocker les informations propres à chaque projet. (Dans les versions antérieures, ce fichier était nommé *NomProj*.vcproj ou *NomProj*.dsp.) Pour obtenir un exemple d’un fichier de projet Visual C++, consultez [fichiers projet](../ide/project-files.md).|  
|*Nomproj*.vcxitems|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *projet d’éléments partagés* fichier. Ce projet n’est pas généré.  Au lieu de cela, le projet peut être référencé par un autre projet C++ et ses fichiers feront partie du processus de génération du projet de référence. Cela permet de partager le code commun avec les projets C++ inter-plateformes.|
|*Nomproj*.sdf|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *base de données de navigation* fichier. Il prend en charge les fonctionnalités de navigation telles que **atteindre la définition**, **rechercher toutes les références**, et **affichage de classes**. Il est généré en analysant les fichiers d'en-tête.|  
|*Nomproj.* vcxproj.filters|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *filtres* fichier. Permet de spécifier l'emplacement d'un fichier ajouté à la solution. Par exemple, un fichier .h est placé dans le **fichiers d’en-tête** nœud.|  
|*Nomproj.* vcxproj.user|*Nomproj*|Non affiché dans l'Explorateur de solutions|Le *utilisateur migration* fichier. Suite à la migration d'un projet à partir de Visual Studio 2008, ce fichier contient des informations qui ont été converties à partir d'un fichier .vsprops.|  
|*Nomproj*.idl|*Nomproj*|Source|(Propre au projet) Contient le code source IDL (Interface Description Langage) d'une bibliothèque de types de contrôles. Visual C++ se sert de ce fichier pour générer une bibliothèque de types. La bibliothèque générée expose l'interface du contrôle aux autres clients Automation. Pour plus d’informations, consultez [fichier IDL (Interface Definition Language)](http://msdn.microsoft.com/library/windows/desktop/aa378712) dans le Kit de développement logiciel Windows.|  
|Readme.txt|*Nomproj*|Projet|Le *Lisez-moi* fichier. Généré par l'Assistant Application, il décrit les fichiers contenus dans un projet.|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)