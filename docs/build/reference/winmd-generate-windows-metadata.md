---
title: "-WINMD (générer des métadonnées Windows) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.GenerateWindowsMetadata
dev_langs: C++
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 903ab6875457aa8c069c47a2be7f8ff1f5c884a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="winmd-generate-windows-metadata"></a>/WINMD (générer des métadonnées Windows)
Active la génération d’un fichier de métadonnées Windows Runtime (.winmd).  
  
```  
/WINMD[:{NO|ONLY}]  
```  
  
## <a name="remarks"></a>Notes  
 /WINMD  
 La valeur par défaut [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] applications. L’éditeur de liens génère le fichier exécutable binaire et le fichier de métadonnées .winmd.  
  
 /WINMD:NO  
 L’éditeur de liens génère le fichier exécutable binaire, mais pas un fichier .winmd.  
  
 / WINMD : UNIQUEMENT  
 L’éditeur de liens génère uniquement le fichier .winmd, mais pas le fichier exécutable binaire.  
  
 Par défaut, le nom de fichier de sortie présente sous la forme `binaryname`.winmd. Pour spécifier un autre nom de fichier, utilisez le [/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) option.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **l’éditeur de liens** dossier.  
  
3.  Sélectionnez le **métadonnées Windows** page de propriétés.  
  
4.  Dans le **générer des métadonnées Windows** liste déroulante, sélectionnez l’option souhaitée.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)