---
title: "-NOLOGO (suppression de la bannière de démarrage) (éditeur de liens) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
dev_langs: C++
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1460563303f6a619d316a1b3ff4f885a31247a72
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Suppression de la bannière de démarrage) (Éditeur de liens)
```  
/NOLOGO  
```  
  
## <a name="remarks"></a>Remarques  
 L’option /NOLOGO empêche l’affichage de l’auteur message et numéro de version.  
  
 Cette option supprime également l’affichage des fichiers de commandes. Pour plus d’informations, consultez [fichiers de commandes LINK](../../build/reference/link-command-files.md).  
  
 Par défaut, ces informations sont transmises par l’éditeur de liens dans la fenêtre Sortie. Sur la ligne de commande, il est envoyé vers une sortie standard et peut être redirigé vers un fichier.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Cette option doit uniquement être utilisée à partir de la ligne de commande.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Cette option de l’éditeur de liens ne peut pas être modifiée par programmation.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)