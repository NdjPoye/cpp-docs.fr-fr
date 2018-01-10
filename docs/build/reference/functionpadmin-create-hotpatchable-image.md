---
title: "-/FUNCTIONPADMIN (création d’Image corrigeable en mémoire) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /functionpadmin
dev_langs: C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f737cdb412420ffb87664024b2314941e67b045b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Création d'une image corrigeable en mémoire)
Prépare une image corrigeable en mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 `space`(facultatif)  
 La quantité de remplissage à ajouter au début de chaque fonction, 5, 6 ou 16.  x86 images requièrent 5 octets de remplissage, x64 images exigent 6 octets et les images générées pour la famille de processeurs Itanium nécessitent 16 octets de remplissage au début de chaque fonction.  
  
 Par défaut, le compilateur ajoute la quantité d’espace correcte à l’image, en fonction du type de l’ordinateur de l’image.  
  
 Pour l’éditeur de liens produire une image corrigeable en mémoire, les fichiers .obj doivent avoir été compilés avec [/hotpatch (créer une Image corrigeable en mémoire)](../../build/reference/hotpatch-create-hotpatchable-image.md).  
  
 Lorsque vous compilez et liez une image avec un appel unique de cl.exe, **/hotpatch** implique **/functionpadmin**.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l’option dans le **des Options supplémentaires** boîte.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)