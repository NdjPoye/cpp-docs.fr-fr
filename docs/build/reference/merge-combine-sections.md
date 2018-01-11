---
title: -MERGE (combiner des Sections) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
dev_langs: C++
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9da4258c1f2b45b2ad6a0dbe3c57cc5f1f304cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="merge-combine-sections"></a>/MERGE (Combiner des sections)
```  
/MERGE:from=to  
```  
  
## <a name="remarks"></a>Notes  
 Cette option associe la première section (*de*) avec la deuxième section (*à*), nommant le résultat *à*. Par exemple, `/merge:.rdata=.text`.  
  
 Si la deuxième section n’existe pas, LINK renomme la section *de* en tant que *à*.  
  
 Cette option est utile pour créer des VxD et en remplaçant les noms de section de généré par le compilateur.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **avancé** page de propriétés.  
  
4.  Modifier la **fusionner les Sections** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)