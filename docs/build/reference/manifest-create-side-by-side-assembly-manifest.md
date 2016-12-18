---
title: "/MANIFEST (Cr&#233;er un manifeste d&#39;assembly c&#244;te &#224; c&#244;te) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateManifest"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFEST (option de l'éditeur de liens)"
  - "MANIFEST (option de l'éditeur de liens)"
  - "-MANIFEST (option de l'éditeur de liens)"
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MANIFEST (Cr&#233;er un manifeste d&#39;assembly c&#244;te &#224; c&#244;te)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## Notes  
 L'option \/MANIFEST spécifie que l'Éditeur de liens doit créer un fichier manifeste côte à côte.  Pour plus d'informations sur les fichiers manifeste, consultez la [référence des fichiers manifeste](http://msdn.microsoft.com/library/aa375632).  
  
 La valeur par défaut est \/MANIFEST.  
  
 L'option \/MANIFEST:EMBED spécifie que l'éditeur de liens doit inclure le fichier manifeste dans l'image comme ressource de type RT\_MANIFEST.  Le paramètre facultatif `ID` est l'ID de ressource à utiliser pour le manifeste.  Utilisez une valeur de 1 pour un fichier exécutable.  Utilisez une valeur de 2 pour une DLL pour lui permettre de spécifier les dépendances privées.  Si le paramètre `ID` n'est pas spécifié, la valeur par défaut est 2 si l'option \/DLL est définie ; sinon, la valeur par défaut est 1.  
  
 À partir de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], les fichiers manifeste pour les fichiers exécutables contiennent une section qui spécifie des informations de contrôle de compte d'utilisateur \(UAC\).  Si vous spécifiez \/MANIFESTE mais ne spécifiez ni [\/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md), ni [\/DLL](../../build/reference/dll-build-a-dll.md), un fragment de contrôle de compte d'utilisateur par défaut dont le niveau de contrôle de compte utilisateur est égal à *asInvoker* est inséré dans le manifeste.  Pour plus d'informations sur les niveaux de contrôle de compte d'utilisateur, consultez [\/MANIFESTUAC \(Incorporer des informations sur le contrôle de compte d'utilisateur dans le manifeste\)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 Pour modifier le comportement par défaut du contrôle de compte d'utilisateur, effectuez une des opérations suivantes :  
  
-   Spécifiez l'option \/MANIFESTUAC et définissez le niveau de contrôle de compte d'utilisateur à la valeur désirée.  
  
-   Ou spécifiez l'option \/MANIFESTUAC:NO si vous ne souhaitez pas générer un fragment de contrôle de compte d'utilisateur dans le manifeste.  
  
 Si vous ne spécifiez pas \/MANIFESTE mais spécifiez des commentaires [\/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md), un fichier manifeste est créé.  Un fichier manifeste n'est pas créé si vous spécifiez \/MANIFESTE:NO.  
  
 Si vous spécifiez \/MANIFEST, le nom du fichier manifeste sera identique à celui de votre fichier de sortie, avec l'extension .manifest ajoutée au nom de fichier.  Par exemple, si votre nom de fichier de sortie est MyFile.exe, le nom du fichier manifeste sera MyFile.exe.manifest.  Si vous spécifiez \/MANIFESTFILE:*name*, le nom du manifeste sera ce que vous aurez spécifié dans *name*.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Fichier manifeste**.  
  
5.  Modifiez la propriété **Génération d'un manifeste**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)