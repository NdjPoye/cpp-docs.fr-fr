---
title: "/NODEFAULTLIB (Ignorer les biblioth&#232;ques) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames"
  - "/nodefaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NODEFAULTLIB (option de l'éditeur de liens)"
  - "bibliothèques par défaut, supprimer"
  - "ignorer les bibliothèques (option de l'éditeur de liens)"
  - "bibliothèques, ignorer"
  - "NODEFAULTLIB (option de l'éditeur de liens)"
  - "-NODEFAULTLIB (option de l'éditeur de liens)"
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NODEFAULTLIB (Ignorer les biblioth&#232;ques)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NODEFAULTLIB[:library]   
```  
  
## Notes  
 où :  
  
 *bibliothèque*  
 désigne une bibliothèque qui sera ignorée par l'éditeur de liens lors de la résolution des références externes.  
  
## Notes  
 L'option \/NODEFAULTLIB indique à l'Éditeur de liens de supprimer une ou plusieurs bibliothèques par défaut dans la liste de recherche des bibliothèques lors de la résolution des références externes.  
  
 Pour créer un fichier .obj qui ne contient pas de référence aux bibliothèques par défaut, utilisez [\/Zl \(Omettre le nom de la bibliothèque par défaut\)](../../build/reference/zl-omit-default-library-name.md).  
  
 Par défaut, cette option supprime toutes les bibliothèques par défaut de la liste des bibliothèques qu'elle parcourt lors de la résolution des références externes.  Le paramètre facultatif *library* vous permet de supprimer une ou plusieurs bibliothèques spécifiées de la liste des bibliothèques qu'elle parcourt lors de la résolution des références externes.  Spécifiez une option \/NODEFAULTLIB pour chaque bibliothèque à exclure.  
  
 L'éditeur de liens résout les références aux définitions externes en recherchant d'abord dans les bibliothèques que vous spécifiez explicitement, puis dans les bibliothèques par défaut spécifiées avec l'option \/DEFAULTLIB et, enfin, dans les bibliothèques par défaut nommées dans les fichiers .obj.  
  
 \/NODEFAULTLIB:*library* substitue [\/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*library* lorsque le même nom de bibliothèque \(*library*\) est spécifié dans les deux options.  
  
 Si vous utilisez \/NODEFAULTLIB, par exemple, pour générer votre programme sans la bibliothèque Runtime C, il se peut que vous deviez également utiliser [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) pour spécifier le point d'entrée \(fonction\) de votre programme.  Pour plus d'informations, consultez [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Entrée**.  
  
4.  Sélectionnez la propriété **Toutes bibliothèques par défaut ignorées** ou spécifiez la liste des bibliothèques que vous souhaitez ignorer dans la propriété **Bibliothèque spécifique ignorée**.  La page de propriétés **Ligne de commande** affichera l'effet des modifications que vous apportez à ces propriétés.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)