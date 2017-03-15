---
title: "/PDBSTRIPPED (Supprimer les symboles priv&#233;s) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbstripped"
  - "VC.Project.VCLinkerTool.StripPrivateSymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pdb, supprimer les symboles privés"
  - "/PDBSTRIPPED (option de l'éditeur de liens)"
  - "fichiers PDB, supprimer les symboles privés"
  - "PDBSTRIPPED (option de l'éditeur de liens)"
  - "-PDBSTRIPPED (option de l'éditeur de liens)"
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDBSTRIPPED (Supprimer les symboles priv&#233;s)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## Notes  
 où :  
  
 *pdb\_file\_name*  
 désigne le nom spécifié par l'utilisateur de la base de données du programme supprimée que l'éditeur de liens crée.  
  
## Notes  
 L'option \/PDBSTRIPPED crée un second fichier PDB \(Program Database\) lorsque vous générez votre image de programme avec toute option du compilateur ou de l'éditeur de liens générant un fichier PDB \([\/DEBUG](../../build/reference/debug-generate-debug-info.md), [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), \/Zd ou \/Zi\).  Ce second fichier PDB omet les symboles que vous ne souhaitez pas envoyer à vos clients.  Il contiendra uniquement :  
  
-   des symboles publics ;  
  
-   la liste des fichiers objets et les portions de l'exécutable auxquelles ils appartiennent ;  
  
-   les enregistrements de débogage FPO \(Frame Pointer Optimization\) utilisés pour traverser la pile.  
  
 Le fichier PDB supprimé ne contiendra pas :  
  
-   Informations de type  
  
-   les informations de numéro de ligne ;  
  
-   les symboles CodeView des fichiers par objet tels que ceux des fonctions, des variables locales et des données statiques.  
  
 Le fichier PDB complet sera toujours généré avec \/PDBSTRIPPED.  
  
 Si vous ne créez pas de fichier PDB, \/PDBSTRIPPED est ignoré.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Déboguer**.  
  
4.  Modifiez la propriété **Suppression des symboles privés**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)