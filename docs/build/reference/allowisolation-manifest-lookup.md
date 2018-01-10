---
title: -/ALLOWISOLATION (recherche de manifeste) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs: C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0ca939021a6fc530b11c6ec66fc74cc012da1c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Recherche de manifeste)
Spécifie un comportement pour la recherche de manifeste.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 **/ALLOWISOLATION:no** indique que les DLL sont chargées comme s’il existait aucun manifeste et entraîne l’éditeur de liens définir le `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit dans l’en-tête optional `DllCharacteristics` champ.  
  
 **/ALLOWISOLATION** provoque le système d’exploitation et charger des manifestes.  
  
 **/ALLOWISOLATION** est la valeur par défaut.  
  
 Lorsque l’isolation est désactivée pour un fichier exécutable, le chargeur Windows ne tente pas à trouver un manifeste d’application pour le processus nouvellement créé. Le nouveau processus ne disposera d’un contexte d’activation par défaut, même s’il existe un manifeste à l’intérieur du fichier exécutable ou dans le même répertoire que le fichier exécutable avec le nom *-nom du fichier exécutable***. exe.manifest**.  
  
 Pour plus d’informations, consultez [référence des fichiers manifeste](http://msdn.microsoft.com/library/aa375632).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **le fichier manifeste** page de propriétés.  
  
5.  Modifier la **autoriser l’Isolation** propriété.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)