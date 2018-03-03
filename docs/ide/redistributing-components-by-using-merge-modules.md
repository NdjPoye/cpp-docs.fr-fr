---
title: "Redistribution des composants à l’aide de Modules de fusion | Documents Microsoft"
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
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 093c732563844b14a3f99662150d4db9b2fac1fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-components-by-using-merge-modules"></a>Redistribution des composants à l’aide de modules de fusion
Visual Studio inclut [de modules de fusion](http://msdn.microsoft.com/library/aa367434) pour chaque composant Visual C++ qui est autorisé à être redistribué par une application. Lorsqu’un module de fusion est compilé dans un fichier d’installation de Windows Installer, il permet le déploiement de certaines DLL sur des ordinateurs comportant une plateforme spécifique. Dans votre fichier d’installation, indiquez que les modules de fusion sont des composants requis pour votre application. Lorsque Visual Studio est installé, les modules de fusion sont installés dans \Program Files\Merge Modules\\. (Seules les versions non debug des DLL Visual C++ peuvent être redistribuées.) Pour plus d’informations et un lien vers une liste des modules de fusion sont concédés sous licence de redistribution, consultez [redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md).  
  
 Vous pouvez utiliser des modules de fusion pour permettre l’installation des DLL Visual C++ redistribuables dans le dossier %SYSTEMROOT%\system32\. (Visual Studio lui-même utilise cette technique). Toutefois, l’installation dans ce dossier échouera à moins que l’utilisateur chargé de l’installation possède des droits d’administrateur.  
  
 Nous vous déconseillons d’utiliser des modules de fusion à moins que vous n’ayez pas à assurer la maintenance de votre application et qu’il n’existe pas de dépendances sur plus d’une version des DLL. Les modules de fusion applicables à différentes versions de la même DLL ne peuvent être inclus dans un programme d’installation. De plus, les modules de fusion rendent difficile la maintenance des DLL indépendamment de l’application. Au lieu de cela, nous vous recommandons d’installer un Package redistribuable de Visual C++.  
  
## <a name="see-also"></a>Voir aussi  
 [Redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md)