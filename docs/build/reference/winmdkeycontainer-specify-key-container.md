---
title: "-WINMDKEYCONTAINER (spécifier un conteneur de clé) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.WINMDKEYCONTAINER
dev_langs: C++
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a7fc567d9b9f4a70c42effec80595b0d33c0cad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (spécifier un conteneur de clé de nom fort)
Spécifie un conteneur de clé pour signer un fichier de métadonnées Windows (.winmd).  
  
```  
/WINMDKEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Remarques  
 Ressemble à la [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) option de l’éditeur de liens qui est appliquée à un fichier (.winmd).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **l’éditeur de liens** dossier.  
  
3.  Sélectionnez le **métadonnées Windows** page de propriétés.  
  
4.  Dans le **conteneur de clé de métadonnées Windows** , entrez l’emplacement.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)