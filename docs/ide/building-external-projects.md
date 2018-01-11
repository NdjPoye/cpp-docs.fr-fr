---
title: "Génération de projets externes | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- external projects
- Visual C++ projects, external projects
- builds [C++], external projects
- projects [C++], external projects
- Makefile projects, external projects
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16b73349a220f392730dd5526fd5f3d59e59754d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="building-external-projects"></a>Génération de projets externes
Un projet externe est un projet Visual C++ qui utilise un makefile ou autres fonctionnalités qui sont en dehors de (étrangère ou externes à) l’environnement de développement Visual C++.  
  
 Si vous avez un projet externe (par exemple, un projet makefile) que vous souhaitez générer dans l’environnement de développement Visual C++, créez un projet Makefile et spécifier de votre projet de générer des commandes et sortie dans l’Assistant Application Makefile. Pour plus d’informations, consultez [création d’un projet Makefile](../ide/creating-a-makefile-project.md).  
  
 Notez que Visual C++ prend en charge n’est plus la possibilité d’exporter un makefile pour le projet actif à partir de l’environnement de développement. Utilisez [commutateurs de ligne de commande Devenv](/visualstudio/ide/reference/devenv-command-line-switches) pour générer des projets Visual Studio sur la ligne de commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Génération de projets C++ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)