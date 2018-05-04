---
title: -DYNAMICBASE (utilisez espace randomisation du format adresse) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85af66c4ce05057eff63292061b66202aeebe160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (Utiliser la randomisation du format d'espace d'adresse)
Spécifie s’il faut générer une image exécutable qui peut être redéfinie de façon aléatoire au moment du chargement à l’aide de la fonctionnalité espace d’adresse (ASLR) de randomisation de [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 Par défaut, /DYNAMICBASE est activé.  
  
 Cette option modifie l’en-tête d’un exécutable pour indiquer si l’application doit être rebasée de façon aléatoire au moment du chargement.  
  
 Randomisation du format d’espace d’adresse est prise en charge sur [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Pour définir cette option d'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **avancé** page de propriétés.  
  
5.  Modifier la **adresse de Base aléatoire** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)