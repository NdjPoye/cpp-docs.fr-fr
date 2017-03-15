---
title: "Syntaxe de la ligne de commande du compilateur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, syntaxe de la ligne de commande"
  - "syntaxe, ligne de commande du compilateur CL"
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Syntaxe de la ligne de commande du compilateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La ligne de commande CL utilise la syntaxe suivante :  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 Le tableau ci\-dessous décrit les entrées de la commande CL.  
  
|Entry|Signification|  
|-----------|-------------------|  
|*Option*|Une ou plusieurs [options CL](../../build/reference/compiler-options.md).  Notez que toutes les options s'appliquent à tous les fichiers source spécifiés.  Ces options sont spécifiées par une barre oblique \(\/\) ou un tiret \(–\).  Si une option accepte des arguments, la description de l'option indique si un espace est admis entre l'option et les arguments.  Les noms des options \(sauf l'option \/HELP\) respectent la casse.  Consultez [Ordre des options CL](../../build/reference/order-of-cl-options.md) pour plus d'informations.|  
|`file`|Nom d'un ou de plusieurs fichiers source, fichiers .obj ou bibliothèques.  CL compile des fichiers source et passe les noms des fichiers .obj et des bibliothèques à l'éditeur de liens.  Pour plus d'informations, consultez [Syntaxe des noms de fichiers CL](../../build/reference/cl-filename-syntax.md).|  
|*lib*|Un ou plusieurs noms de bibliothèques.  CL passe ces noms à l'éditeur de liens.|  
|*command\-file*|Fichier qui contient plusieurs options et noms de fichiers.  Pour plus d'informations, consultez [Fichiers de commandes CL](../../build/reference/cl-command-files.md).|  
|*link\-opt*|Une ou plusieurs [options de l'éditeur de liens](../../build/reference/linker-options.md).  CL passe ces options à l'éditeur de liens.|  
  
 Vous pouvez spécifier n'importe quel nombre d'options, de noms de fichiers et de noms de bibliothèques, du moment que le nombre de caractères sur la ligne de commande ne dépasse pas 1 024, la limite imposée par le système d'exploitation.  
  
 Pour plus d'informations sur la valeur de retour de cl.exe, consultez [Valeur de retour de cl.exe](../../build/reference/return-value-of-cl-exe.md).  
  
> [!NOTE]
>  Il n'est pas certain que la limite d'entrée sur la ligne de commande \(1 024 caractères\) reste inchangée dans les versions futures de Windows.  
  
## Voir aussi  
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)