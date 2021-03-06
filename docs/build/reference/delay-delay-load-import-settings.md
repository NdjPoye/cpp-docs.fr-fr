---
title: -DELAY (paramètres d’importation chargement différé) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c898727504a8ae530bcdffb3e01bde68c31c8e87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Paramètres d'importation à chargement différé)
```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## <a name="remarks"></a>Notes  
 L’option /DELAY contrôle [chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md) des DLL :  
  
-   Le qualificateur UNLOAD indique à la fonction d'assistance de chargement différé de prendre en charge le déchargement explicite de la DLL. La table IAT (Import Address Table) est réinitialisée à sa forme d'origine, ce qui invalide les pointeurs IAT et entraîne leur remplacement.  
  
     Si vous ne sélectionnez pas UNLOAD, tout appel à [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) échoue.  
  
-   Le qualificateur NOBIND indique à l'éditeur de liens de ne pas inclure dans l'image finale de table IAT pouvant être liée. L'option par défaut consiste à créer la table IAT pouvant être liée pour les DLL chargées en différé. L'image obtenue ne peut pas être liée statiquement. (Les images avec des tables IAT pouvant être liées sont susceptibles d'être liées statiquement avant leur exécution.) Consultez [/lier](../../build/reference/bind.md).  
  
     Si la DLL est liée, la fonction d’assistance tente d’utiliser les informations liées au lieu d’appeler [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) sur chaque importation référencée. Si l'horodatage ou l'adresse préférée ne correspondent pas à ceux de la DLL chargée, la fonction d'assistance suppose que la table IAT liée est obsolète et continuera comme si la table IAT liée n'existe pas.  
  
     NOBIND augmente la taille de votre image de programme mais peut réduire le temps de chargement de la DLL. Si vous n'avez pas l'intention de lier la DLL, NOBIND empêchera la création de la table IAT liée.  
  
 Pour spécifier les DLL pour différer le chargement, utilisez la [DELAYLOAD](../../build/reference/delayload-delay-load-import.md) option.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez **propriétés de Configuration**, **l’éditeur de liens**, puis sélectionnez **avancé**.  
  
3.  Modifier la **chargement différé des DLL** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)