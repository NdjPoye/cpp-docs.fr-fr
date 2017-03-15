---
title: "/FA, /Fa (Fichier listing) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AssemblerListingLocation"
  - "VC.Project.VCCLCompilerTool.ConfigureASMListing"
  - "VC.Project.VCCLWCECompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.AssemblerListingLocation"
  - "/fa"
  - "VC.Project.VCCLCompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FA (option du compilateur C++)"
  - "listing du code assembleur uniquement"
  - "FA (option du compilateur C++)"
  - "-FA (option du compilateur C++)"
  - "type de fichier listing"
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /FA, /Fa (Fichier listing)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un fichier listing qui contient le code assembleur.  
  
## Syntaxe  
  
```  
/FA[c|s|u]  
/Fapathname  
```  
  
## Notes  
 Les arguments déterminent la génération du code source et du code machine ainsi que l'extension du fichier listing.  
  
 Le tableau suivant décrit les différentes valeurs de **\/FA**.  Il est possible de spécifier plusieurs valeurs pour **\/FA**.  Par exemple, vous pouvez effectuer **\/FAsu**.  
  
|Option|Contenu du listing et extension de fichier|  
|------------|------------------------------------------------|  
|**\/FA**|Code assembleur ; .asm|  
|**\/FAc**|Code assembleur et machine ; .cod|  
|**\/FAs**|Code assembleur et source ; .asm<br /><br /> Si **\/FAcs** est spécifié, l'extension de fichier est .cod|  
|**\/FAu**|Entraîne la création du fichier de sortie au format UTF\-8, avec un marqueur d'ordre d'octet.  Par défaut, l'encodage de fichier est ANSI, mais utilisez **\/FAu** si vous souhaitez un fichier listing qui s'affiche correctement sur tout système, ou si vous utilisez des fichiers de code source Unicode comme entrées dans le compilateur.<br /><br /> Si **\/FAsu** est spécifié, et si un fichier de code source utilise un encodage Unicode autre que UTF\-8, les lignes de code contenues dans le fichier .asm risquent de ne pas s'afficher correctement.|  
  
 Par défaut, le fichier listing prend le même nom de base que le fichier source.  Vous pouvez modifier le nom du fichier listing et le répertoire où il est créé à l'aide de l'option **\/Fa**.  
  
|Utilisation de \/Fa|Résultat|  
|-------------------------|--------------|  
|**\/Fa**|Un *source\_file*.asm est créé pour chaque fichier de code source de la compilation.|  
|**\/Fa** *filename*|*filename*.asm est placé dans le répertoire courant.  Valide seulement lors de la compilation d'un seul fichier de code source.|  
|**\/Fa** *filename.extension*|*filename.extension* est placé dans le répertoire courant.  Valide seulement lors de la compilation d'un seul fichier de code source.|  
|**\/Fa** *directory*\\|Un *source\_file*.asm est créé et placé dans le répertoire *directory* spécifié pour chaque fichier de code source de la compilation.  Notez la présence de la barre oblique inverse obligatoire.  Seuls les chemins d'accès sur le disque actif sont admis.|  
|**\/Fa** *directory*\\*filename*|*filename*.asm est placé dans le répertoire `directory`spécifié.  Valide seulement lors de la compilation d'un seul fichier de code source.|  
|**\/Fa** *directory*\\*filename.extension*|*filename.extension* est placé dans le répertoire `directory`spécifié.  Valide seulement lors de la compilation d'un seul fichier de code source.|  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Fichiers de sortie**.  
  
4.  Modifiez la propriété **Emplacement d'un listing ASM** \(**\/Fa**\) ou **Sortie de l'assembleur** \(**\/FA**\) \(**\/FAu** doit être spécifié dans la page de propriétés **Ligne de commande**, zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> ou <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>.  Pour spécifier **\/FAu**, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Exemple  
 La ligne de commande suivante produit un listing appelé HELLO.cod combinant code source et code machine :  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)