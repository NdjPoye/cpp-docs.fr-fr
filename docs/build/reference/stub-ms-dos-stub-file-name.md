---
title: "/STUB (Nom du fichier stub MS-DOS) | Microsoft Docs"
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
  - "/stub"
  - "VC.Project.VCLinkerTool.DosStub"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/STUB (option de l'éditeur de liens)"
  - "nom du fichier stub MS-DOS (option de l'éditeur de liens)"
  - "STUB (option de l'éditeur de liens)"
  - "-STUB (option de l'éditeur de liens)"
  - "Win32 (C++), attacher le programme stub MS-DOS"
  - "API Windows (C++), attacher le programme stub MS-DOS"
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STUB (Nom du fichier stub MS-DOS)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STUB:filename  
```  
  
## Notes  
 où :  
  
 *filename*  
 est une application MS\-DOS.  
  
## Notes  
 L'option \/STUB attache un programme stub MS\-DOS à un programme Win32.  
  
 Un programme stub est appelé si le fichier est exécuté sous MS\-DOS.  En général, il affiche un message approprié même si toute application MS\-DOS valide peut faire office de programme stub.  
  
 Spécifiez l'argument *filename* pour le programme stub après le signe deux\-points \(:\) sur la ligne de commande.  L'éditeur de liens le vérifie et émet un message d'erreur si le fichier n'est pas un exécutable.  Le programme doit être un fichier .exe ; un fichier .com n'est pas valide pour un programme stub.  
  
 Si cette option n'est pas utilisée, l'éditeur de liens attache un programme stub par défaut qui affiche le message suivant :  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 Lors de la génération d'un pilote de périphérique virtuel, l'argument *filename* permet à l'utilisateur de spécifier un nom de fichier contenant une structure IMAGE\_DOS\_HEADER \(définie dans WINNT.H\) à utiliser dans le pilote VxD, à la place de l'en\-tête par défaut.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Tapez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)