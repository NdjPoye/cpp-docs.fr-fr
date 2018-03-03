---
title: "-PGD (spécifier la base de données pour les optimisations guidées par profil) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb61395d9f3b8c98e17e3683a7c3897b9315d78b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Spécifier la base de données pour les optimisations guidées par profil)
/ PGD :`filename`  
  
## <a name="remarks"></a>Notes  
 où :  
  
 `filename`  
 Spécifie le nom du fichier .pgd qui sera utilisé pour conserver les informations sur le programme en cours d’exécution.  
  
## <a name="remarks"></a>Notes  
 Lorsque vous utilisez [/LTCG : PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md), employez /PGD pour spécifier un autre nom ou emplacement pour le fichier .pgd. Si vous ne spécifiez pas/PGD, le nom du fichier .pgd doit être le même que le nom de fichier sortie (.exe ou .dll) et sera créé dans le même répertoire que celui à partir duquel la liaison a été appelée.  
  
 Lors de l’utilisation / LTCG : PGOPTIMIZE, employez /PGD pour spécifier le nom du fichier .pgd à utiliser pour créer l’image optimisée.  
  
 Pour plus d’informations, consultez [optimisation guidée par profil](../../build/reference/profile-guided-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **optimisation** page de propriétés.  
  
5.  Modifier la **base de données guidée par profil** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)