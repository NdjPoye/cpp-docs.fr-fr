---
title: Génération de projets externes | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- external projects
- Visual C++ projects, external projects
- builds [C++], external projects
- projects [C++], external projects
- Makefile projects, external projects
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97b6aa1e5939afe55644df6529bf75ba043f20bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="building-external-projects"></a>Génération de projets externes
Un projet externe est un projet Visual C++ qui utilise un makefile ou autres fonctionnalités qui sont en dehors de (étrangère ou externes à) l’environnement de développement Visual C++.  
  
 Si vous avez un projet externe (par exemple, un projet makefile) que vous souhaitez générer dans l’environnement de développement Visual C++, créez un projet Makefile et spécifier de votre projet de générer des commandes et sortie dans l’Assistant Application Makefile. Pour plus d’informations, consultez [création d’un projet Makefile](../ide/creating-a-makefile-project.md).  
  
 Notez que Visual C++ prend en charge n’est plus la possibilité d’exporter un makefile pour le projet actif à partir de l’environnement de développement. Utilisez [commutateurs de ligne de commande Devenv](/visualstudio/ide/reference/devenv-command-line-switches) pour générer des projets Visual Studio sur la ligne de commande.  
  
## <a name="see-also"></a>Voir aussi  
 [Génération de projets C++ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)