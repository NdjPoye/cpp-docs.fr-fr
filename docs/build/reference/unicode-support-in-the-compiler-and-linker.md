---
title: "Prise en charge Unicode dans le compilateur et l&#39;&#233;diteur de liens | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCLibrarianTool.UseUnicodeResponseFiles"
  - "VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode, Visual C++"
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Prise en charge Unicode dans le compilateur et l&#39;&#233;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit la prise en charge Unicode dans les outils de génération Visual C\+\+.  
  
 Noms de fichiers  
 Les noms de fichiers spécifiés sur la ligne de commande ou dans les directives du compilateur \(telles que \#include\), peuvent désormais contenir des caractères Unicode.  
  
 Fichiers de code source  
 Les caractères Unicode sont désormais pris en charge dans les identificateurs, les macros, les littéraux de chaîne et de caractère, ainsi que dans les commentaires.  Les noms de caractères universels sont également pris en charge.  
  
 Des caractères Unicode peuvent être entrés dans un fichier de code source en respectant les encodages suivants :  
  
-   UTF\-16 little endian avec ou sans marque d'ordre d'octet \(BOM, Byte Order Mark\)  
  
-   UTF\-16 big endian avec ou sans BOM  
  
-   UTF\-8 avec BOM  
  
 Sortie  
 Pendant la compilation, le compilateur génère des diagnostics sur la console au format UTF\-16.  Les caractères qui peuvent être affichés sur votre console dépendent des propriétés de la fenêtre de console.  La sortie de compilateur redirigée vers un fichier se trouve dans la page de codes de la console ANSI actuelle.  
  
 Fichiers réponse et fichiers .DEF de l'éditeur de liens  
 Les fichiers réponse et les fichiers DEF peuvent être au format UTF\-16 avec une marque d'ordre d'octet \(Byte Order Mark, BOM\) ou au format ANSI.  Précédemment, seul le format ANSI était pris en charge.  
  
 dumps .asm et .cod  
 Les dumps .asm et .cod sont par défaut au format ANSI à des fins de compatibilité avec MASM.  Utilisez \/FAu pour produire du code UTF\-8.  Notez que si vous spécifiez \/Fa, la source mélangée sera directement affichée et pourra sembler altérée, par exemple si le code source est au format UTF\-8 et que vous n'avez pas spécifié \/FAsu.  
  
 Vous pouvez activer les noms de fichiers Unicode dans l'environnement de développement \(consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md)\) en sélectionnant l'outil approprié et en sélectionnant la propriété **Utilisation de fichiers réponse UNICODE** qui est activée par défaut.  Vous pouvez décider de modifier cette valeur par défaut pour certaines raisons, notamment si vous modifiez votre environnement de développement pour utiliser un compilateur qui n'offre pas la prise en charge d'Unicode.  
  
## Voir aussi  
 [Génération à partir de la ligne de commande](../../build/building-on-the-command-line.md)