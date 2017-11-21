---
title: "-/MANIFESTDEPENDENCY (spécifier les dépendances de manifeste) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs: C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 070adfa51103d2ab91b371918107aa432ee5aa70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Spécifier les dépendances de manifeste)
```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## <a name="remarks"></a>Remarques  
 /MANIFESTDEPENDENCY vous permet de spécifier des attributs qui seront placés dans le \<dépendance > section du fichier manifeste.  
  
 Consultez [/MANIFEST (manifeste d’Assembly créer côte à côte)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) pour plus d’informations sur la création d’un fichier manifeste.  
  
 Pour plus d’informations sur la \<dépendance > section du fichier manifeste, consultez [les fichiers de Configuration de serveur de publication](http://msdn.microsoft.com/library/aa375682).  
  
 Les informations /MANIFESTDEPENDENCY peuvent être passées à l’éditeur de liens de deux manières :  
  
-   Directement sur la ligne de commande (ou dans un fichier réponse) avec /MANIFESTDEPENDENCY.  
  
-   Via le [commentaire](../../preprocessor/comment-c-cpp.md) pragma.  
  
 L’exemple suivant illustre un commentaire /MANIFESTDEPENDENCY passé via ce pragma :  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 ce qui entraîne l’entrée suivante dans le fichier manifeste :  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Les mêmes commentaires /MANIFESTDEPENDENCY peuvent être passés à la ligne de commande comme suit :  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 L’éditeur de liens sera collecter les commentaires /MANIFESTDEPENDENCY, éliminer les entrées en double, puis ajoutez la chaîne XML qui en résulte dans le fichier manifeste.  Si l’éditeur de liens recherche d’entrées en conflit, le fichier manifeste est endommagé et l’application ne pourront pas lancer (une entrée peut être ajoutée au journal des événements, indiquant la source de l’échec).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **le fichier manifeste** page de propriétés.  
  
5.  Modifier la **dépendances de manifeste supplémentaires** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)