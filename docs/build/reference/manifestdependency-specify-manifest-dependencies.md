---
title: "/MANIFESTDEPENDENCY (Sp&#233;cifier les d&#233;pendances de manifeste) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.AdditionalManifestDependencies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTDEPENDENCY (option de l'éditeur de liens)"
  - "MANIFESTDEPENDENCY (option de l'éditeur de liens)"
  - "-MANIFESTDEPENDENCY (option de l'éditeur de liens)"
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFESTDEPENDENCY (Sp&#233;cifier les d&#233;pendances de manifeste)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFESTDEPENDENCY:manifest_dependency  
```  
  
## Notes  
 \/MANIFESTDEPENDENCY vous permet de spécifier des attributs qui seront placés dans la section \<dépendance\> du fichier manifeste.  
  
 Consultez [\/MANIFEST \(Créer un manifeste d'assembly côte à côte\)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) pour plus d'informations sur la création d'un fichier manifeste.  
  
 Pour plus d'informations sur la section \<dépendance\> du fichier manifeste, consultez [Fichiers de Configuration de Publieur](http://msdn.microsoft.com/library/aa375682).  
  
 Les informations \/MANIFESTDEPENDENCY peuvent être passées à l'éditeur de liens de deux manières :  
  
-   directement sur la ligne de commande \(ou dans un fichier réponse\) avec \/MANIFESTDEPENDENCY ;  
  
-   via le pragma [comment](../../preprocessor/comment-c-cpp.md).  
  
 L'exemple suivant affiche un commentaire \/MANIFESTDEPENDENCY passé via ce pragma :  
  
```  
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")  
```  
  
 qui entraîne l'entrée suivante dans le fichier manifeste :  
  
```  
<dependency>  
  <dependentAssembly>  
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />  
  </dependentAssembly>  
</dependency>  
```  
  
 Les mêmes commentaires \/MANIFESTDEPENDENCY peuvent être passés au niveau de la ligne de commande comme suit :  
  
```  
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"  
```  
  
 L'éditeur de liens recueille les commentaires \/MANIFESTDEPENDENCY, élimine les entrées en double, puis ajoute la chaîne XML résultante au fichier manifeste.  S'il détecte des entrées en conflit, le fichier manifeste est endommagé et l'application ne peut pas s'exécuter \(une entrée peut être ajoutée au journal des événements, en indiquant la source de l'échec\).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Fichier manifeste**.  
  
5.  Modifiez la propriété **Dépendances de manifeste supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)